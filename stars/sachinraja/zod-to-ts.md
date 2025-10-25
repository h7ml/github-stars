---
project: zod-to-ts
stars: 391
description: generate TypeScript types from your Zod schema
url: https://github.com/sachinraja/zod-to-ts
---

zod-to-ts
=========

Generate TypeScript types from your Zod schema.

Installation
------------

```
npm install zod-to-ts
```

This package has peer dependencies of zod@4 and typescript@5.

Usage
-----

import { z } from 'zod'
import { zodToTs, createAuxiliaryTypeStore } from 'zod-to-ts'

const UserSchema \= z.object({
	username: z.string(),
	age: z.number(),
	inventory: z.object({
		name: z.string(),
		itemId: z.number(),
	}).array(),
})

const auxiliaryTypeStore \= createAuxiliaryTypeStore()
const { node } \= zodToTs(UserSchema, { auxiliaryTypeStore })

`node`

{
    username: string;
    age: number;
    inventory: {
        name: string;
        itemId: number;
    }\[\];
}

`node` is a TypeScript AST node that represents the TypeScript type corresponding to the input Zod schema.

`zodToTs` only returns the type node, not the actual type declaration. If you want to create a type declaration, you can use the `createTypeAlias` utility.

import { createTypeAlias, zodToTs } from 'zod-to-ts'

const typeAlias \= createTypeAlias(node, 'User')

`node`

type User \= {
    username: string;
    age: number;
    inventory: {
        name: string;
        itemId: number;
    }\[\];
};

If you want to get the node as a string, you can use the `printNode` utility.

import { printNode } from 'zod-to-ts'

const nodeString \= printNode(node)
console.log(nodeString)

You can also use it with `createTypeAlias`.

import { createTypeAlias, printNode } from 'zod-to-ts'

const typeAlias \= createTypeAlias(node, 'User')
const nodeString \= printNode(typeAlias)
console.log(nodeString)

Configuration
-------------

You can pass options in the second argument to `zodToTs`.

zodToTs(schema, {
	...
})

### `metadataRegistry`

Metadata for schemas is currently only used for comments for nodes. If a schema has a `description` field associated with it then a JSDoc comment with the description is added for that schema. This is set to the global registry by default.

### `unrepresentable`

The following APIs are not representable in `zod-to-ts`. They cannot accurately be represented as TypeScript types as they cannot be statically analyzed. By default an error will be thrown if they are encountered, but if `unrepresentable` is set to `'any'` then the type will be set to `any` for these APIs.

z.transform() // ❌
z.custom(); // ❌

### `io`

This changes whether to extract the schema's input or output type as these can be different when APIs such as `.pipe()` are used. It can be set to `'input'` or `'output'`, `'output'` is the default.

Auxiliary Types
---------------

By now you might be wondering what `auxiliaryTypeStore` actually does and rightfully so. Due to recursion, it's impossible to represent every type with just a single type declaration. Some may require auxiliary/helper types alongside the main type node for correctness.

import { z } from 'zod'
import { createAuxiliaryTypeStore, zodToTs } from 'zod-to-ts'

const Category \= z.object({
  name: z.string(),
  get subcategories(){
    return z.array(Category)
  }
})

const auxiliaryTypeStore \= createAuxiliaryTypeStore()
const { node } \= zodToTs(Category, { auxiliaryTypeStore })

`node`

Auxiliary\_0

Wait what happened to the types for the node? Why is it just a type reference? Let's examine the `auxiliaryTypeStore` map.

{
	identifier: \`Auxiliary\_0\`,
	node: \`type Auxiliary\_0 = {
		name: string,
		subcategories: Auxiliary\_0,
	}\`
}

So this is where our types went! An auxiliary type had to be created to properly reflect the recursion.

To extract all the auxiliary types from the store you can use the following code.

const auxiliaryTypeStore \= createAuxiliaryTypeStore()
const { node } \= zodToTs(Category, { auxiliaryTypeStore })

const auxiliaryTypePreamble \= auxiliaryTypeStore.definitions
	.values()
	.toArray()
	.map((definition) \=> printNode(definition.node))
	.join('\\n')

const categoryTypeAlias \= createTypeAlias(node, 'Category')
const categoryType \= printNode(categoryTypeAlias)

const outputFile \= \`${auxiliaryTypePreamble}\\n${categoryType}\`
console.log(outputFile)

`outputFile`

type Auxiliary\_0 \= {
    name: string;
    subcategories: Auxiliary\_0\[\];
};
type Category \= Auxiliary\_0;

Auxiliary type stores are intended to be used across multiple `zodToTs` calls so they can be reused.

import { z } from 'zod'
import { createAuxiliaryTypeStore, zodToTs } from 'zod-to-ts'

const Category \= z.object({
  name: z.string(),
  get subcategories(){
    return z.array(Category)
  }
})

const Post \= z.object({
	id: z.number(),
	categories: z.array(Category),
})

const auxiliaryTypeStore \= createAuxiliaryTypeStore()
const { node: categoryNode } \= zodToTs(Category, { auxiliaryTypeStore })
const { node: postNode } \= zodToTs(Post, { auxiliaryTypeStore })

Now if we check the store after both these calls, we still only see the single type from before.

`categoryNode`

Auxiliary\_0

`postNode`

{
    id: number;
    categories: Auxiliary\_0\[\];
}

Overriding Types
----------------

You can specify a map of type overrides to override a type with a provided TS AST node, which is useful when more information is needed to determine the actual type than can be statically inferred.

import { z } from 'zod'
import { createAuxiliaryTypeStore, type TypeOverrideMap, zodToTs } from 'zod-to-ts'

const overrides: TypeOverrideMap \= new Map()

const DateSchema \= z.instanceof(Date)
overrides.set(DateSchema, (ts) \=>
	ts.factory.createTypeReferenceNode(ts.factory.createIdentifier('Date')),
)

const ItemSchema \= z.object({
	name: z.string(),
	date: DateSchema,
})

const auxiliaryTypeStore \= createAuxiliaryTypeStore()
const { node } \= zodToTs(ItemSchema, {
	auxiliaryTypeStore,
	overrides,
})

Without the override this will throw an error that `custom` types like `instanceof` are unrepresentable.

With the override, it will return this node.

{
    name: string;
    date: Date;
}
