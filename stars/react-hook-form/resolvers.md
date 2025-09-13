---
project: resolvers
stars: 2102
description: 📋 Validation resolvers: Yup, Zod, Superstruct, Joi, Vest, Class Validator, io-ts, Nope, computed-types, typanion, Ajv, TypeBox, ArkType, Valibot, effect-ts, VineJS and Standard Schema
url: https://github.com/react-hook-form/resolvers
---

Performant, flexible and extensible forms with easy to use validation.

React Hook Form Resolvers
-------------------------

This function allows you to use any external validation library such as Yup, Zod, Joi, Vest, Ajv and many others. The goal is to make sure you can seamlessly integrate whichever validation library you prefer. If you're not using a library, you can always write your own logic to validate your forms.

Install
-------

Install your preferred validation library alongside `@hookform/resolvers`.

```
npm install @hookform/resolvers # npm
yarn add @hookform/resolvers # yarn
pnpm install @hookform/resolvers # pnpm
bun install @hookform/resolvers # bun
```

Resolver Comparison

resolver

Infer values  
from schema

criteriaMode

AJV

❌

`firstError | all`

Arktype

✅

`firstError`

class-validator

✅

`firstError | all`

computed-types

✅

`firstError`

Effect

✅

`firstError | all`

fluentvalidation-ts

❌

`firstError`

io-ts

✅

`firstError`

joi

❌

`firstError | all`

Nope

❌

`firstError`

Standard Schema

✅

`firstError | all`

Superstruct

✅

`firstError`

typanion

✅

`firstError`

typebox

✅

`firstError | all`

typeschema

❌

`firstError | all`

valibot

✅

`firstError | all`

vest

❌

`firstError | all`

vine

✅

`firstError | all`

yup

✅

`firstError | all`

zod

✅

`firstError | all`

TypeScript
----------

Most of the resolvers can infer the output type from the schema. See comparison table for more details.

useForm<Input, Context, Output\>()

Example:

import { useForm } from 'react-hook-form';
import { zodResolver } from '@hookform/resolvers/zod';
import { z } from 'zod'; // or 'zod/v4'

const schema \= z.object({
  id: z.number(),
});

// Automatically infers the output type from the schema
useForm({
  resolver: zodResolver(schema),
});

// Force the output type
useForm<z.input<typeof schema\>, any, z.output<typeof schema\>\>({
  resolver: zodResolver(schema),
});

Links
-----

-   React-hook-form validation resolver documentation

### Supported resolvers

-   React Hook Form Resolvers
-   Install
-   TypeScript
-   Links
    -   Supported resolvers
-   API
-   Quickstart
    -   Yup
    -   Zod
    -   Superstruct
    -   Joi
    -   Vest
    -   Class Validator
    -   io-ts
    -   Nope
    -   computed-types
    -   typanion
    -   Ajv
    -   TypeBox
        -   With `ValueCheck`
        -   With `TypeCompiler`
    -   ArkType
    -   Valibot
    -   TypeSchema
    -   effect-ts
    -   VineJS
    -   fluentvalidation-ts
    -   standard-schema
-   Backers
-   Contributors

API
---

```
type Options = {
  mode: 'async' | 'sync',
  raw?: boolean
}

resolver(schema: object, schemaOptions?: object, resolverOptions: Options)
```

type

Required

Description

schema

`object`

✓

validation schema

schemaOptions

`object`

validation library schema options

resolverOptions

`object`

resolver options, `async` is the default mode

Quickstart
----------

### Yup

Dead simple Object schema validation.

import { useForm } from 'react-hook-form';
import { yupResolver } from '@hookform/resolvers/yup';
import \* as yup from 'yup';

const schema \= yup
  .object()
  .shape({
    name: yup.string().required(),
    age: yup.number().required(),
  })
  .required();

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: yupResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('name')} /\>
      <input type\="number" {...register('age')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### Zod

TypeScript-first schema validation with static type inference

> ⚠️ Example below uses the `valueAsNumber`, which requires `react-hook-form` v6.12.0 (released Nov 28, 2020) or later.

import { useForm } from 'react-hook-form';
import { zodResolver } from '@hookform/resolvers/zod';
import { z } from 'zod'; // or 'zod/v4'

const schema \= z.object({
  name: z.string().min(1, { message: 'Required' }),
  age: z.number().min(10),
});

const App \= () \=> {
  const {
    register,
    handleSubmit,
    formState: { errors },
  } \= useForm({
    resolver: zodResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('name')} />
      {errors.name?.message && <p\>{errors.name?.message}</p\>}
      <input type\="number" {...register('age', { valueAsNumber: true })} />
      {errors.age?.message && <p\>{errors.age?.message}</p\>}
      <input type\="submit" />
    </form\>
  );
};

### Superstruct

A simple and composable way to validate data in JavaScript (or TypeScript).

import { useForm } from 'react-hook-form';
import { superstructResolver } from '@hookform/resolvers/superstruct';
import { object, string, number } from 'superstruct';

const schema \= object({
  name: string(),
  age: number(),
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: superstructResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('name')} /\>
      <input type\="number" {...register('age', { valueAsNumber: true })} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### Joi

The most powerful data validation library for JS.

import { useForm } from 'react-hook-form';
import { joiResolver } from '@hookform/resolvers/joi';
import Joi from 'joi';

const schema \= Joi.object({
  name: Joi.string().required(),
  age: Joi.number().required(),
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: joiResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('name')} /\>
      <input type\="number" {...register('age')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### Vest

Vest 🦺 Declarative Validation Testing.

import { useForm } from 'react-hook-form';
import { vestResolver } from '@hookform/resolvers/vest';
import { create, test, enforce } from 'vest';

const validationSuite \= create((data \= {}) \=> {
  test('username', 'Username is required', () \=> {
    enforce(data.username).isNotEmpty();
  });

  test('password', 'Password is required', () \=> {
    enforce(data.password).isNotEmpty();
  });
});

const App \= () \=> {
  const { register, handleSubmit, errors } \= useForm({
    resolver: vestResolver(validationSuite),
  });

  return (
    <form onSubmit\={handleSubmit((data) \=> console.log(data))}\>
      <input {...register('username')} /\>
      <input type\="password" {...register('password')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### Class Validator

Decorator-based property validation for classes.

> ⚠️ Remember to add these options to your `tsconfig.json`!

```
"strictPropertyInitialization": false,
"experimentalDecorators": true
```

import { useForm } from 'react-hook-form';
import { classValidatorResolver } from '@hookform/resolvers/class-validator';
import { Length, Min, IsEmail } from 'class-validator';

class User {
  @Length(2, 30)
  username: string;

  @IsEmail()
  email: string;
}

const resolver \= classValidatorResolver(User);

const App \= () \=> {
  const {
    register,
    handleSubmit,
    formState: { errors },
  } \= useForm<User\>({ resolver });

  return (
    <form onSubmit\={handleSubmit((data) \=> console.log(data))}\>
      <input type\="text" {...register('username')} />
      {errors.username && <span\>{errors.username.message}</span\>}
      <input type\="text" {...register('email')} />
      {errors.email && <span\>{errors.email.message}</span\>}
      <input type\="submit" value\="Submit" />
    </form\>
  );
};

### io-ts

Validate your data with powerful decoders.

import React from 'react';
import { useForm } from 'react-hook-form';
import { ioTsResolver } from '@hookform/resolvers/io-ts';
import t from 'io-ts';
// you don't have to use io-ts-types, but it's very useful
import tt from 'io-ts-types';

const schema \= t.type({
  username: t.string,
  age: tt.NumberFromString,
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: ioTsResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      <input type\="number" {...register('age')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

export default App;

### Nope

A small, simple, and fast JS validator

import { useForm } from 'react-hook-form';
import { nopeResolver } from '@hookform/resolvers/nope';
import Nope from 'nope-validator';

const schema \= Nope.object().shape({
  name: Nope.string().required(),
  age: Nope.number().required(),
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: nopeResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('name')} /\>
      <input type\="number" {...register('age')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### computed-types

TypeScript-first schema validation with static type inference

import { useForm } from 'react-hook-form';
import { computedTypesResolver } from '@hookform/resolvers/computed-types';
import Schema, { number, string } from 'computed-types';

const schema \= Schema({
  username: string.min(1).error('username field is required'),
  age: number,
});

const App \= () \=> {
  const {
    register,
    handleSubmit,
    formState: { errors },
  } \= useForm({
    resolver: computedTypesResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('name')} />
      {errors.name?.message && <p\>{errors.name?.message}</p\>}
      <input type\="number" {...register('age', { valueAsNumber: true })} />
      {errors.age?.message && <p\>{errors.age?.message}</p\>}
      <input type\="submit" />
    </form\>
  );
};

### typanion

Static and runtime type assertion library with no dependencies

import { useForm } from 'react-hook-form';
import { typanionResolver } from '@hookform/resolvers/typanion';
import \* as t from 'typanion';

const isUser \= t.isObject({
  username: t.applyCascade(t.isString(), \[t.hasMinLength(1)\]),
  age: t.applyCascade(t.isNumber(), \[
    t.isInteger(),
    t.isInInclusiveRange(1, 100),
  \]),
});

const App \= () \=> {
  const {
    register,
    handleSubmit,
    formState: { errors },
  } \= useForm({
    resolver: typanionResolver(isUser),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('name')} />
      {errors.name?.message && <p\>{errors.name?.message}</p\>}
      <input type\="number" {...register('age')} />
      {errors.age?.message && <p\>{errors.age?.message}</p\>}
      <input type\="submit" />
    </form\>
  );
};

### Ajv

The fastest JSON validator for Node.js and browser

import { useForm } from 'react-hook-form';
import { ajvResolver } from '@hookform/resolvers/ajv';

// must use \`minLength: 1\` to implement required field
const schema \= {
  type: 'object',
  properties: {
    username: {
      type: 'string',
      minLength: 1,
      errorMessage: { minLength: 'username field is required' },
    },
    password: {
      type: 'string',
      minLength: 1,
      errorMessage: { minLength: 'password field is required' },
    },
  },
  required: \['username', 'password'\],
  additionalProperties: false,
};

const App \= () \=> {
  const {
    register,
    handleSubmit,
    formState: { errors },
  } \= useForm({
    resolver: ajvResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((data) \=> console.log(data))}\>
      <input {...register('username')} />
      {errors.username && <span\>{errors.username.message}</span\>}
      <input {...register('password')} />
      {errors.password && <span\>{errors.password.message}</span\>}
      <button type\="submit"\>submit</button\>
    </form\>
  );
};

### TypeBox

JSON Schema Type Builder with Static Type Resolution for TypeScript

#### With `ValueCheck`

import { useForm } from 'react-hook-form';
import { typeboxResolver } from '@hookform/resolvers/typebox';
import { Type } from '@sinclair/typebox';

const schema \= Type.Object({
  username: Type.String({ minLength: 1 }),
  password: Type.String({ minLength: 1 }),
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: typeboxResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      <input type\="password" {...register('password')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

#### With `TypeCompiler`

A high-performance JIT of `TypeBox`, read more

import { useForm } from 'react-hook-form';
import { typeboxResolver } from '@hookform/resolvers/typebox';
import { Type } from '@sinclair/typebox';
import { TypeCompiler } from '@sinclair/typebox/compiler';

const schema \= Type.Object({
  username: Type.String({ minLength: 1 }),
  password: Type.String({ minLength: 1 }),
});

const typecheck \= TypeCompiler.Compile(schema);

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: typeboxResolver(typecheck),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      <input type\="password" {...register('password')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### ArkType

TypeScript's 1:1 validator, optimized from editor to runtime

import { useForm } from 'react-hook-form';
import { arktypeResolver } from '@hookform/resolvers/arktype';
import { type } from 'arktype';

const schema \= type({
  username: 'string>1',
  password: 'string>1',
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: arktypeResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      <input type\="password" {...register('password')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### Valibot

The modular and type safe schema library for validating structural data

import { useForm } from 'react-hook-form';
import { valibotResolver } from '@hookform/resolvers/valibot';
import \* as v from 'valibot';

const schema \= v.object({
  username: v.pipe(
    v.string('username is required'),
    v.minLength(3, 'Needs to be at least 3 characters'),
    v.endsWith('cool', 'Needs to end with \`cool\`'),
  ),
  password: v.string('password is required'),
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: valibotResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      <input type\="password" {...register('password')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### TypeSchema

Universal adapter for schema validation, compatible with any validation library

import { useForm } from 'react-hook-form';
import { typeschemaResolver } from '@hookform/resolvers/typeschema';
import { z } from 'zod';

// Use your favorite validation library
const schema \= z.object({
  username: z.string().min(1, { message: 'Required' }),
  password: z.number().min(1, { message: 'Required' }),
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: typeschemaResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      <input type\="password" {...register('password')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

### effect-ts

A powerful TypeScript framework that provides a fully-fledged functional effect system with a rich standard library.

import React from 'react';
import { useForm } from 'react-hook-form';
import { effectTsResolver } from '@hookform/resolvers/effect-ts';
import { Schema } from 'effect';

const schema \= Schema.Struct({
  username: Schema.String.pipe(
    Schema.nonEmptyString({ message: () \=> 'username required' }),
  ),
  password: Schema.String.pipe(
    Schema.nonEmptyString({ message: () \=> 'password required' }),
  ),
});

type FormData \= typeof schema.Type;

interface Props {
  onSubmit: (data: FormData) \=> void;
}

function TestComponent({ onSubmit }: Props) {
  const {
    register,
    handleSubmit,
    formState: { errors },
    // provide generic if TS has issues inferring types
  } \= useForm<FormData\>({
    resolver: effectTsResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit(onSubmit)}\>
      <input {...register('username')} /\>
      {errors.username && <span role\="alert"\>{errors.username.message}</span\>}

      <input {...register('password')} /\>
      {errors.password && <span role\="alert"\>{errors.password.message}</span\>}

      <button type\="submit"\>submit</button\>
    </form\>
  );
}

### VineJS

VineJS is a form data validation library for Node.js

import { useForm } from 'react-hook-form';
import { vineResolver } from '@hookform/resolvers/vine';
import vine from '@vinejs/vine';

const schema \= vine.compile(
  vine.object({
    username: vine.string().minLength(1),
    password: vine.string().minLength(1),
  }),
);

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: vineResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      {errors.username && <span role\="alert"\>{errors.username.message}</span\>}
      <input {...register('password')} /\>
      {errors.password && <span role\="alert"\>{errors.password.message}</span\>}
      <button type\="submit"\>submit</button\>
    </form\>
  );
};

### fluentvalidation-ts

A TypeScript-first library for building strongly-typed validation rules

import { useForm } from 'react-hook-form';
import { fluentValidationResolver } from '@hookform/resolvers/fluentvalidation-ts';
import { Validator } from 'fluentvalidation-ts';

class FormDataValidator extends Validator<FormData\> {
  constructor() {
    super();

    this.ruleFor('username')
      .notEmpty()
      .withMessage('username is a required field');
    this.ruleFor('password')
      .notEmpty()
      .withMessage('password is a required field');
  }
}

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: fluentValidationResolver(new FormDataValidator()),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      {errors.username && <span role\="alert"\>{errors.username.message}</span\>}
      <input {...register('password')} /\>
      {errors.password && <span role\="alert"\>{errors.password.message}</span\>}
      <button type\="submit"\>submit</button\>
    </form\>
  );
};

### standard-schema

A standard interface for TypeScript schema validation libraries

Example zod

import { useForm } from 'react-hook-form';
import { standardSchemaResolver } from '@hookform/resolvers/standard-schema';
import { z } from 'zod';

const schema \= z.object({
  name: z.string().min(1, { message: 'Required' }),
  age: z.number().min(10),
});

const App \= () \=> {
  const {
    register,
    handleSubmit,
    formState: { errors },
  } \= useForm({
    resolver: standardSchemaResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('name')} /\>
      {errors.name?.message && <p\>{errors.name?.message}</p\>}
      <input type\="number" {...register('age', { valueAsNumber: true })} /\>
      {errors.age?.message && <p\>{errors.age?.message}</p\>}
      <input type\="submit" /\>
    </form\>
  );
};

Example arkType

import { useForm } from 'react-hook-form';
import { standardSchemaResolver } from '@hookform/resolvers/standard-schema';
import { type } from 'arktype';

const schema \= type({
  username: 'string>1',
  password: 'string>1',
});

const App \= () \=> {
  const { register, handleSubmit } \= useForm({
    resolver: standardSchemaResolver(schema),
  });

  return (
    <form onSubmit\={handleSubmit((d) \=> console.log(d))}\>
      <input {...register('username')} /\>
      <input type\="password" {...register('password')} /\>
      <input type\="submit" /\>
    </form\>
  );
};

Backers
-------

Thanks go to all our backers! \[Become a backer\].

Contributors
------------

Thanks go to these wonderful people! \[Become a contributor\].
