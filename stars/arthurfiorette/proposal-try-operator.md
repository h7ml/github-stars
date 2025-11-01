---
project: proposal-try-operator
stars: 1906
description: A proposal to bring ergonomic, inline error handling to JavaScript through a new try operator that always returns a Result.
url: https://github.com/arthurfiorette/proposal-try-operator
---

  

ECMAScript Try Operator
=======================

Tip

You can test the runtime aspect of this proposal and its ergonomics today! Install our reference `Result` class implementation from NPM:

`npm install try`

  

  

This proposal addresses the ergonomic challenges of managing multiple, often nested, `try/catch` blocks necessary for handling operations that may fail at various points.

Only the `catch (error) {}` block represents actual control flow, while no program state inherently depends on being inside a `try {}` block. Therefore, forcing the successful flow into nested blocks is not ideal.

  

-   Status
-   Authors
-   Try/Catch Is Not Enough
-   Caller's Approach
-   Try Operator
    -   Expressions are evaluated in a self-contained `try/catch` block
    -   Can be inlined.
    -   Any valid expression can be used
        -   `await` is not a special case
    -   Statements are not expressions
    -   Never throws
    -   Parenthesis Required for Object Literals
    -   Void Operations
-   Result Class
    -   Reference Implementation
    -   Instance Structure
    -   Iterable Protocol
    -   Manual Creation
    -   `try()` static method
    -   No Result Flattening
-   What This Proposal Does Not Aim to Solve
    -   Type-Safe Errors
    -   Automatic Error Handling
-   Why Not `data` First?
-   The Need for an `ok` Value
-   A Case for Syntax
-   Why This Belongs in the Language
-   Help Us Improve This Proposal
-   Inspiration
-   License

  

Status
------

**Stage:** 0  
**Champion:** _Actively looking for one_

_For more information see the TC39 proposal process._

  

Authors
-------

-   Arthur Fiorette (X)
-   Arlen Beiler

  

Try/Catch Is Not Enough
-----------------------

The `try {}` block often feels redundant because its scoping lacks meaningful conceptual significance. Rather than serving as an essential control flow construct, it mostly acts as a code annotation. Unlike loops or conditionals, a `try {}` block doesn’t encapsulate any distinct program state that requires isolation.

On the other hand, the `catch {}` block **is** genuine control flow, making its scoping relevant. According to Oxford Languages, an exception is defined as:

> a person or thing that is excluded from a general statement or does not follow a rule.

Since catch explicitly handles exceptions, encapsulating exception-handling logic in a dedicated block makes sense. Following the same reasoning, there is no justification for also enclosing the non-exceptional flow in a block.

Consider a simple function like this:

function getPostInfo(session, postSlug, cache, db) {
  const user \= cache.getUser(session.userId)

  const post \= db.selectPost(postSlug, user)
  const comments \= db.selectComments(post.id, user)

  return { post, comments }
}

But **production code is rarely this clean**. Error handling quickly forces a messier structure:

function getPostInfo(session, postSlug, cache, db) {
  let user

  // Requires a dedicated error handler
  try {
    user \= cache.getUser(session.userId)
  } catch (error) {
    otel.capture(error, Operations.GET\_SELF)
    session.logout()
    throw new Error("Invalid session")
  }

  // No recovery if selectPost fails
  try {
    const post \= db.selectPost(postSlug, user)

    let comments \= \[\]

    // The post must still be returned even if fetching comments fails
    try {
      comments \= db.selectComments(post.id, user)
    } catch (error) {
      otel.capture(error, Operations.JOIN\_POST\_COMMENTS)
    }
  } catch (error) {
    otel.capture(error, Operations.GET\_POST)
    throw new Error("Could not get post")
  }

  return { post, comments }
}

The `try` blocks didn't provide much value beyond introducing unnecessary nesting.

Instead, using the proposed `try` operator simplifies the function:

function getPostInfo(session, postId, cache, db) {
  const \[userOk, userErr, user\] \= try cache.getUser(session.userId)

  // Requires a dedicated error handler
  if (!userOk) {
    session.logout()

    otel.capture(userErr, Operations.GET\_SELF)
    throw new Error("Invalid session")
  }

  const \[postOk, postErr, post\] \= try db.selectPost(postId, user)

  // No recovery if selectPost fails
  if (!postOk) {
    otel.capture(postErr, Operations.GET\_POST)
    throw new Error("Could not get post")
  }

  const \[commentsOk, commentsErr, comments \= \[\]\] \= try db.selectComments(post.id, user)

  // The post must still be returned even if fetching comments fails
  if (!commentsOk) {
    otel.capture(commentsErr, Operations.JOIN\_POST\_COMMENTS)
  }

  return { post, comments }
}

This approach improves readability by cleanly separating the happy path from error handling.

Control flow remains linear, making it easier to follow, while only the "exceptions" in execution require explicit scoping.

The result is a more structured, maintainable function where failures are handled concisely without unnecessary indentation.

  

Caller's Approach
-----------------

JavaScript has evolved over decades, with countless libraries and codebases built on top of one another. Any new feature that does not consider compatibility with existing code risks negatively impacting its adoption, as refactoring functional, legacy code simply to accommodate a new feature is often an unjustifiable cost.

With that in mind, improvements in error handling can be approached in two ways:

1.  **At the caller's level**:
    
    try {
      const value \= work()
    } catch (error) {
      console.error(error)
    }
    
2.  **At the callee's level**:
    
    function work() {
      try {
        // Performs some operation
    
        return { ok: true, value }
      } catch (error) {
        return { ok: false, error }
      }
    }
    

Both approaches achieve the same goal, but the second one requires refactoring all implementations into a new format. This is how languages like Go and Rust handle errors, returning a tuple of an error and a value or a `Result` object, respectively. While the callee-based approach can arguably be better, it succeeded in those languages because it was adopted from the very beginning, rather than introduced as a later addition.

This proposal accounts for this by moving the transformation of errors into values to the **caller** level, preserving the familiar semantics and placement of `try/catch`. This approach ensures backward compatibility with existing code.

Breaking compatibility is unacceptable for platforms like Node.js or libraries. Consequently, a callee-based approach would likely never be adopted for functions like `fetch` or `fs.readFile`, as it would disrupt existing codebases.

Ironically, **these are precisely the kinds of functions where improved error handling is most needed**.

  

Try Operator
------------

The `try` operator consists of the `try` keyword followed by an expression. It results in an instance of the `Result`.

All of its usages are just a combination of the above said rules.

// wraps the result of \`something()\` in a Result
const a \= try something()

// Result is iterable
const \[ok, err, val\] \= try something()

// Result still is iterable
const \[\[ok, err, val\]\] \= \[try something()\]

// Result\[\]
array.map(fn \=> try fn())

// yields Result
yield try something()

// Result<T> where T is the argument of iterator().next(arg: T) but also captures
// any error thrown by something()
try yield something()

// Result<Awaited<ReturnType<typeof something>>>
try await something()

// catches TypeError: Right-hand side of 'instanceof' is not an object
try (a instanceof b)

// Result<boolean> instanceof boolean
(try a) instanceof Result

// Result<Result<Result<Result<Result<number>>>
const a \= try (try (try (try (try 1))))

### Expressions are evaluated in a self-contained `try/catch` block

const result \= try expression

This is "equivalent" to:

let \_result
try {
  \_result \= Result.ok(expression)
} catch (error) {
  \_result \= Result.error(error)
}
const result \= \_result

### Can be inlined.

Similar to `void`, `typeof`, `yield`, and `new`:

array.map((fn) \=> try fn()).filter((result) \=> result.ok)

### Any valid expression can be used

const result \= try data?.someProperty.anotherFunction?.(await someData()).andAnotherOne()

This is "equivalent" to:

let \_result
try {
  \_result \= Result.ok(
    data?.someProperty.anotherFunction?.(await someData()).andAnotherOne()
  )
} catch (error) {
  \_result \= Result.error(error)
}
const result \= \_result

#### `await` is not a special case

const result \= try await fetch("https://arthur.place")

Which is only valid in async contexts and equates to:

let \_result
try {
  \_result \= Result.ok(await fetch("https://arthur.place"))
} catch (error) {
  \_result \= Result.error(error)
}
const result \= \_result

### Statements are not expressions

const result \= try throw new Error("Something went wrong") // Syntax error!
const result \= try using resource \= new Resource() // Syntax error!

This is because their "equivalent" would also result in a syntax error:

let \_result
try {
  \_result \= Result.ok(throw new Error("Something went wrong")) // Syntax error!
} catch (error) {
  \_result \= Result.error(error)
}
const result \= \_result

A detailed discussion about this topic is available at GitHub Issue #54 for those interested.

### Never throws

The `try` operator ensures that no error escapes its scope:

const \[ok, error, result\] \= try some.thing()

Regardless of the type of error that might occur, `try` will catch it. For example:

-   If `some` is `undefined`.
-   If `thing` is not a function.
-   If accessing the `thing` property on `some` throws an error.
-   Any other exception that can arise on that line of code.

All potential errors are safely caught and encapsulated within the `try` operator expression.

### Parenthesis Required for Object Literals

When using `try` with an object literal, the literal must be enclosed in parenthesis:

const result \= try ({ data: await work() })

This behavior mirrors how JavaScript differentiates blocks and object literals:

 { a: 1 }  // empty block with a label
({ a: 1 }) // object with a key \`a\` and a number \`1\`

A detailed discussion about this topic is available at GitHub Issue #55 for those interested.

### Void Operations

In scenarios where the successful result of an operation is not needed, it can be safely ignored:

function work() {
  try fs.unlinkSync("temp.txt")
}

This behavior aligns with common patterns, such as using `await` on asynchronous operations where the result is not utilized:

await fs.promises.unlink("temp.txt")

While it is valid to ignore the result, tools like TypeScript ESLint may introduce similar rules, such as `no-floating-promises`, to encourage developers to explicitly indicate that the result is being ignored. A common workaround to provide a visual cue is to use `void` alongside `try`:

function work() {
  // This approach works without modification and provides a clear hint
  void try fs.unlinkSync("temp.txt")
}

  

Result Class
------------

The `try` operator evaluates an expression and returns an instance of the `Result` class, which encapsulates the outcome of the operation.

### Reference Implementation

To validate the ergonomics and utility of this proposal, a spec-compliant, runtime-only implementation of the `Result` class has been published to npm as the `try` package. This package provides a `t()` function that serves as a polyfill for the `try` operator's runtime behavior, allowing developers to experiment with the core pattern.

import { t } from "try"

const \[ok, err, val\] \= await t(fetch, "https://arthur.place")

You can check the published package at npmjs.com/package/try or github.com/arthurfiorette/try and contribute to its development.

### Instance Structure

A `Result` instance always contains a boolean `ok` property that indicates the outcome.

-   If `ok` is `true`, the instance also has a `value` property containing the successful result.
-   If `ok` is `false`, it has an `error` property containing the thrown exception.

Crucially, a success result does not have an `error` property, and a failure result does not have a `value` property. This allows for reliable checks like `'error' in result`.

const result \= try something()

if (result.ok) {
  console.log(result.value)
} else {
  console.error(result.error)
}

### Iterable Protocol

To support ergonomic destructuring, `Result` instances are iterable. They yield their state in the order `[ok, error, value]`, allowing for clear, inline handling of both success and failure cases.

const \[success, validationError, user\] \= try User.parse(myJson)

### Manual Creation

While the `try` operator is the primary source of `Result` instances, they can also be created manually using static methods. This is useful for testing or for bridging with APIs that do not use exceptions.

// Create a successful result
const success \= Result.ok(42)

// Create a failure result
const failure \= Result.error(new Error("Operation failed"))

### `try()` static method

It also includes a static `Result.try()` method, which serves as the runtime foundation for the `try` operator. This method wraps a function call, catching any synchronous exceptions or asynchronous rejections and returning a `Result` or `Promise<Result>`, respectively.

The proposed `try expression` syntax is essentially an ergonomic improvement over the more verbose `Result.try(() => expression)`, removing the need for a function wrapper.

### No Result Flattening

The `try` operator and `Result` constructors wrap the value they are given without inspection. If this value is itself a `Result` instance, it will be nested, not flattened. This ensures predictable and consistent behavior.

  

What This Proposal Does Not Aim to Solve
----------------------------------------

### Type-Safe Errors

The `throw` statement in JavaScript can throw any type of value. This proposal does not impose nor propose any kind of safety around error handling.

-   No generic error type for the proposed Result class will be added.
-   No catch branching based on error type will be added. See GitHub Issue #43 for more information.
-   No way to annotate a callable to specify the error type it throws will be added.

For more information, also see microsoft/typescript#13219.

### Automatic Error Handling

While this proposal facilitates error handling, it does not automatically handle errors for you. You will still need to write the necessary code to manage errors the proposal simply aims to make this process easier and more consistent.

  

Why Not `data` First?
---------------------

In Go, the convention is to place the data variable first, and you might wonder why we don't follow the same approach in JavaScript. In Go, this is the standard way to call a function. However, in JavaScript, we already have the option to use `const data = fn()` and choose to ignore the error, which is precisely the issue this proposal seeks to address.

If someone is using a `try` statement, it is because they want to ensure they handle errors and avoid neglecting them. Placing the data first would undermine this principle by prioritizing the result over error handling.

// This line doesn't acknowledge the possibility of errors being thrown
const data \= fn()

// It's easy to forget to add a second error parameter
const \[data\] \= try fn()

// This approach gives all clues to the reader about the 2 possible states
const \[ok, error, data\] \= try fn()

If you want to suppress the error (which is **different** from ignoring the possibility of a function throwing an error), you can do the following:

// This suppresses a possible error (Ignores and doesn't re-throw)
const \[ok, , data\] \= try fn()

This approach is explicit and readable, as it acknowledges the possibility of an error while indicating that you do not care about it.

The above method, often referred to as "try-catch calaboca" (a Brazilian term), can also be written as:

let ok \= true
let data
try {
  data \= fn()
} catch {
  ok \= false
}

A detailed discussion about this topic is available at GitHub Issue #13 for those interested.

  

The Need for an `ok` Value
--------------------------

The idea of `throw x` doing _anything_ other than throwing `x` is inherently flawed. Wrapping the `error` in an object disregards this principle and introduces unnecessary ambiguity.

Consider the following pseudocode, which might seem harmless but is actually risky:

function doWork() {
  if (check) {
    throw createException(Errors.SOMETHING\_WENT\_WRONG)
  }

  return work()
}

const \[error, data\] \= try doWork()

if (!error) {
  user.send(data)
}

There is no guarantee that `createException` always returns an exception. Someone could even mistakenly write `throw null` or `throw undefined`, both of which are valid but undesired JavaScript code.

Even though such cases are uncommon, they can occur. The `ok` value is crucial to mitigate these runtime risks effectively.

For a more in-depth explanation of this decision, refer to GitHub Issue #30.

  

A Case for Syntax
-----------------

This proposal intentionally combines the `try` operator with the `Result` class because one is incomplete without the other. The `try` operator standardizes the many attempts at safely catching synchronous function calls (the way we can with Promise `.catch` for async calls). Consistency is key, and the `try` syntax establishes common patterns for all developers.

It has been suggested that a runtime-only proposal for the `Result` class might face less resistance within the TC39 process. While this strategic viewpoint is understood, this proposal deliberately presents a unified feature. Separating the runtime from the syntax severs the solution from its motivating problem. It would ask the committee to standardize a `Result` object whose design is justified by a syntax **that doesn't yet exist**.

Without the `try` operator, the `Result` class is just one of many possible library implementations, not a definitive language feature. We believe the feature must be evaluated on its complete ergonomic and practical merits, which is only possible when the syntax and runtime are presented together.

  

Why This Belongs in the Language
--------------------------------

A proposal doesn’t need to introduce a feature that is entirely impossible to achieve otherwise. In fact, most recent proposals primarily reduce the complexity of tasks that are already achievable by providing built-in conveniences.

The absence of a `Result`\-like type and a standard pattern for safely wrapping function calls has led to widespread ecosystem fragmentation. The NPM registry contains hundreds of variations attempting to implement safe wrapping of function calls, and countless more exist as private, copy-pasted utilities. This leaves developers with a poor choice: risk adopting a library that may be abandoned, or contribute to the problem by creating yet another bespoke implementation.

This is the same problem that optional chaining (`?.`) and nullish coalescing (`??`) solved. **They replaced a landscape of competing utilities with a single, trusted language feature**. By standardizing this pattern, we provide a reliable primitive that developers can use with confidence, knowing it is a stable and permanent part of JavaScript.

It also creates a shared foundation between developers and package authors. Everyone can rely on the same Result implementation without compatibility concerns. The goal is to end the fragmentation and establish a foundational tool for robust error handling.

  

Help Us Improve This Proposal
-----------------------------

This proposal is in its early stages, and we welcome your input to help refine it. Please feel free to open an issue or submit a pull request with your suggestions.

**_Any contribution is welcome!_**

  

Inspiration
-----------

-   This tweet from @LeaVerou
-   The frequent oversight of error handling in JavaScript code.
-   Effect TS Error Management
-   The `tuple-it` npm package, which introduces a similar concept but modifies the `Promise` and `Function` prototypes.
-   Szymon Wygnański for donating the `try` package name on NPM to host the reference implementation of this proposal.

  

License
-------

This proposal is licensed under the MIT License.
