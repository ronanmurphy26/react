<div align="center">
<h1>React+TypeScript Cheatsheets</h1>

<a href="https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/81">
  <img
    height="90"
    width="90"
    alt="react + ts logo"
    src="https://user-images.githubusercontent.com/6764957/53868378-2b51fc80-3fb3-11e9-9cee-0277efe8a927.png"
    align="left"
  />
</a>

<p>Cheatsheets for experienced React developers getting started with TypeScript</p>

[**Web docs**](https://react-typescript-cheatsheet.netlify.app/docs/basic/setup) |
[中文翻译](https://github.com/fi3ework/blog/tree/master/react-typescript-cheatsheet-cn) |
[**Español**](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet-es) |
[Contribute!](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/blob/master/CONTRIBUTING.md) |
[Ask!](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new/choose)

</div>

---

<div align="center">

:wave: This repo is maintained by [@swyx](https://twitter.com/swyx), [@ferdaber](https://twitter.com/ferdaber), [@eps1lon](https://twitter.com/sebsilbermann), [@jsjoeio](https://twitter.com/jsjoeio) and [@arvindcheenu](https://twitter.com/arvincheenu), we're so happy you want to try out TypeScript with React! If you see anything wrong or missing, please [file an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new/choose)! :+1:

</div>

---

## All React + TypeScript Cheatsheets

- **The Basic Cheatsheet** ([`/README.md`](/README.md#basic-cheatsheet-table-of-contents)) is focused on helping React devs just start using TS in React **apps**
  - Focus on opinionated best practices, copy+pastable examples.
  - Explains some basic TS types usage and setup along the way.
  - Answers the most Frequently Asked Questions.
  - Does not cover generic type logic in detail. Instead we prefer to teach simple troubleshooting techniques for newbies.
  - The goal is to get effective with TS without learning _too much_ TS.
- **The Advanced Cheatsheet** ([`/ADVANCED.md`](https://react-typescript-cheatsheet.netlify.app/docs/advanced/intro)) helps show and explain advanced usage of generic types for people writing reusable type utilities/functions/render prop/higher order components and TS+React **libraries**.
  - It also has miscellaneous tips and tricks for pro users.
  - Advice for contributing to DefinitelyTyped.
  - The goal is to take _full advantage_ of TypeScript.
- **The Migrating Cheatsheet** ([`/MIGRATING.md`](https://react-typescript-cheatsheet.netlify.app/docs/migration/intro)) helps collate advice for incrementally migrating large codebases from JS or Flow, **from people who have done it**.
  - We do not try to convince people to switch, only to help people who have already decided.
  - ⚠️This is a new cheatsheet, all assistance is welcome.
- **The HOC Cheatsheet** ([`/HOC.md`](https://react-typescript-cheatsheet.netlify.app/docs/hoc/intro)) specifically teaches people to write HOCs with examples.
  - Familiarity with [Generics](https://www.typescriptlang.org/docs/handbook/generics.html) is necessary.
  - ⚠️This is the newest cheatsheet, all assistance is welcome.

---

### Basic Cheatsheet Table of Contents

<details>

<summary><b>Expand Table of Contents</b></summary>

- [Section 1: Setup TypeScript with React](#section-1-setup-typescript-with-react)
  - [Prerequisites](#prerequisites)
  - [React + TypeScript Starter Kits](#react--typescript-starter-kits)
  - [Import React](#import-react)
- [Section 2: Getting Started](#section-2-getting-started)
  - [Function Components](#function-components)
  - [Hooks](#hooks)
  - [useState](#usestate)
  - [useReducer](#usereducer)
  - [useEffect](#useeffect)
  - [useRef](#useref)
  - [useImperativeHandle](#useimperativehandle)
  - [Custom Hooks](#custom-hooks)
  - [Class Components](#class-components)
  - [You May Not Need `defaultProps`](#you-may-not-need-defaultprops)
  - [Typing `defaultProps`](#typing-defaultprops)
  - [Consuming Props of a Component with defaultProps](#consuming-props-of-a-component-with-defaultprops)
    - [Problem Statement](#problem-statement)
    - [Solution](#solution)
  - [Misc Discussions and Knowledge](#misc-discussions-and-knowledge)
  - [Types or Interfaces?](#types-or-interfaces)
  - [Basic Prop Types Examples](#basic-prop-types-examples)
  - [Useful React Prop Type Examples](#useful-react-prop-type-examples)
  - [getDerivedStateFromProps](#getderivedstatefromprops)
  - [Forms and Events](#forms-and-events)
  - [Context](#context)
  - [Basic Example](#basic-example)
  - [Extended Example](#extended-example)
  - [forwardRef/createRef](#forwardrefcreateref)
  - [Portals](#portals)
  - [Error Boundaries](#error-boundaries)
    - [Option 1: Using react-error-boundary](#option-1-using-react-error-boundary)
    - [Options 2: Writing your custom error boundary component](#options-2-writing-your-custom-error-boundary-component)
  - [Concurrent React/React Suspense](#concurrent-reactreact-suspense)
- [Troubleshooting Handbook: Types](#troubleshooting-handbook-types)
  - [Union Types and Type Guarding](#union-types-and-type-guarding)
  - [Optional Types](#optional-types)
  - [Enum Types](#enum-types)
  - [Type Assertion](#type-assertion)
  - [Simulating Nominal Types](#simulating-nominal-types)
  - [Intersection Types](#intersection-types)
  - [Union Types](#union-types)
  - [Overloading Function Types](#overloading-function-types)
  - [Using Inferred Types](#using-inferred-types)
  - [Using Partial Types](#using-partial-types)
  - [The Types I need weren't exported!](#the-types-i-need-werent-exported)
  - [The Types I need don't exist!](#the-types-i-need-dont-exist)
    - [Slapping `any` on everything](#slapping-any-on-everything)
    - [Autogenerate types](#autogenerate-types)
    - [Typing Exported Hooks](#typing-exported-hooks)
    - [Typing Exported Components](#typing-exported-components)
- [Troubleshooting Handbook: Operators](#troubleshooting-handbook-operators)
- [Troubleshooting Handbook: Utilities](#troubleshooting-handbook-utilities)
- [Troubleshooting Handbook: tsconfig.json](#troubleshooting-handbook-tsconfigjson)
- [Troubleshooting Handbook: Fixing bugs in official typings](#troubleshooting-handbook-fixing-bugs-in-official-typings)
- [Troubleshooting Handbook: Globals, Images and other non-TS files](#troubleshooting-handbook-globals-images-and-other-non-ts-files)
- [Other React + TypeScript resources](#other-react--typescript-resources)
- [Editor Tooling and Integration](#editor-tooling-and-integration)
- [Linting](#linting)
- [Other React + TypeScript resources](#other-react--typescript-resources-1)
- [Recommended React + TypeScript talks](#recommended-react--typescript-talks)
- [Time to Really Learn TypeScript](#time-to-really-learn-typescript)
- [Example App](#example-app)
- [My question isn't answered here!](#my-question-isnt-answered-here)
  - [Contributors](#contributors)
  <!--START-SECTION:setup-toc-->
  - [Prerequisites](#prerequisites)
  - [React + TypeScript Starter Kits](#react--typescript-starter-kits)
  - [Import React](#import-react)<!--END-SECTION:setup-toc-->
- [Section 2: Getting Started](#section-2-getting-started)
  - [Function Components](#function-components)
  - [Hooks](#hooks)
  - [Class Components](#class-components)
  - [Typing defaultProps](#typing-defaultprops)
  - [Types or Interfaces?](#types-or-interfaces)
  - [Basic Prop Types Examples](#basic-prop-types-examples)
  - [Useful React Prop Type Examples](#useful-react-prop-type-examples)
  - [getDerivedStateFromProps](#getDerivedStateFromProps)
  - [Forms and Events](#forms-and-events)
  - [Context](#context)
  - [forwardRef/createRef](#forwardrefcreateref)
  - [Portals](#portals)
  - [Error Boundaries](#error-boundaries)
  - [Concurrent React/React Suspense](#concurrent-reactreact-suspense)
- [Basic Troubleshooting Handbook: Types](#basic-troubleshooting-handbook-types)
  <!--START-SECTION:types-toc-->
  - [Union Types and Type Guarding](#union-types-and-type-guarding)
  - [Optional Types](#optional-types)
  - [Enum Types](#enum-types)
  - [Type Assertion](#type-assertion)
  - [Simulating Nominal Types](#simulating-nominal-types)
  - [Intersection Types](#intersection-types)
  - [Union Types](#union-types)
  - [Overloading Function Types](#overloading-function-types)
  - [Using Inferred Types](#using-inferred-types)
  - [Using Partial Types](#using-partial-types)
  - [The Types I need weren't exported!](#the-types-i-need-werent-exported)
  - [The Types I need don't exist!](#the-types-i-need-dont-exist)
    - [Slapping `any` on everything](#slapping-any-on-everything)
    - [Autogenerate types](#autogenerate-types)
    - [Typing Exported Hooks](#typing-exported-hooks)
    - [Typing Exported Components](#typing-exported-components)<!--END-SECTION:types-toc-->
- [Troubleshooting Handbook: Operators](#troubleshooting-handbook-operators)
- [Troubleshooting Handbook: Utilties](#troubleshooting-handbook-utilities)
- [Troubleshooting Handbook: tsconfig.json](#troubleshooting-handbook-tsconfigjson)
- [Troubleshooting Handbook: Bugs in official typings](#troubleshooting-handbook-bugs-in-official-typings)
- [Recommended React + TypeScript codebases to learn from](#recommended-react--typescript-codebases-to-learn-from)
- [Editor Tooling and Integration](#editor-tooling-and-integration)
- [Linting](#linting)
- [Other React + TypeScript resources](#other-react--typescript-resources)
- [Recommended React + TypeScript talks](#recommended-react--typescript-talks)
- [Time to Really Learn TypeScript](#time-to-really-learn-typescript)
- [Example App](#example-app)
- [My question isn't answered here!](#my-question-isnt-answered-here)
  </details>

<!--START-SECTION:setup-->

# Section 1: Setup TypeScript with React

## Prerequisites

1. good understanding of [React](https://reactjs.org)
2. familiarity with [TypeScript Types](https://www.typescriptlang.org/docs/handbook/basic-types.html) ([2ality's guide](http://2ality.com/2018/04/type-notation-typescript.html) is helpful. If you’re an absolute beginner in TypeScript, check out [chibicode’s tutorial](https://ts.chibicode.com/todo/).)
3. having read [the TypeScript section in the official React docs](https://reactjs.org/docs/static-type-checking.html#typescript).
4. having read [the React section of the new TypeScript playground](http://www.typescriptlang.org/play/index.html?jsx=2&esModuleInterop=true&e=181#example/typescript-with-react) (optional: also step through the 40+ examples under [the playground's](http://www.typescriptlang.org/play/index.html) Examples section)

This guide will always assume you are starting with the latest TypeScript version. Notes for older versions will be in expandable `<details>` tags.

## React + TypeScript Starter Kits

Cloud setups:

- [TypeScript Playground with React](https://www.typescriptlang.org/play?#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcA5FDvmQNwCwAUKJLHAN5wCuqWAyjMhhYANFx4BRAgSz44AXzhES5Snhi1GjLAA8W8XBAB2qeAGEInQ0KjjtycABsscALxwAFAEpXAPnaM4OANjeABtA0sYUR4Yc0iAXVcxPgEhdwAGT3oGAOTJaXx3L19-BkDAgBMIXE4QLCsAOhhgGCckgAMATQsgh2BcAGssCrgAEjYIqwVmutR27MC5LM0yuEoYTihDD1zAgB4K4AA3H13yvbAfbs5e-qGRiYspuBmsVD2Aekuz-YAjThgMCMcCMpj6gxcbGKLj8MTiVnck3gAGo4ABGTxyU6rcrlMF3OB1H5wT7-QFGbG4z6HE65ZYMOSMIA) just if you are debugging types (and reporting issues), not for running code
- [CodeSandbox](http://ts.react.new) - cloud IDE, boots up super fast
- [Stackblitz](https://stackblitz.com/edit/react-typescript-base) - cloud IDE, boots up super fast

Local dev setups:

- [Next.js](https://nextjs.org/docs/basic-features/typescript): `npx create-next-app -e with-typescript` will create in your current folder
- [Create React App](https://facebook.github.io/create-react-app/docs/adding-typescript): `npx create-react-app name-of-app --template typescript` will create in new folder
- [Meteor](https://guide.meteor.com/build-tool.html#typescript): `meteor create --typescript name-of-my-new-typescript-app`
- [Ignite](https://github.com/infinitered/ignite#use-ignite-andross-infinite-red-andross-boilerplate) for React Native: `ignite new myapp`
- [TSDX](https://tsdx.io/): `npx tsdx create mylib` for Creating React+TS libraries

<details>
<summary>
Other tools
</summary>

Less mature tools still worth checking out:

- [Vite](https://twitter.com/swyx/status/1282727239230996480?lang=en): `npm init vite-app my-react-project --template react-ts` (note - not yet v1.0, but very fast)
- [Snowpack](<https://www.snowpack.dev/#create-snowpack-app-(csa)>): `npx create-snowpack-app my-app --template app-template-react-typescript`
- [Docusaurus v2](https://v2.docusaurus.io/docs/installation) with [TypeScript Support](https://v2.docusaurus.io/docs/typescript-support)
- [Parcel](https://v2.parceljs.org/languages/typescript/)

Manual setup:

- [Basarat's guide](https://github.com/basarat/typescript-react/tree/master/01%20bootstrap) for **manual setup** of React + TypeScript + Webpack + Babel
- In particular, make sure that you have `@types/react` and `@types/react-dom` installed ([Read more about the DefinitelyTyped project if you are unfamiliar](https://definitelytyped.org/))
- There are also many React + TypeScript boilerplates, please see [our Other Resources list](https://react-typescript-cheatsheet.netlify.app/docs/basic/recommended/resources/).

</details>

## Import React

```tsx
import * as React from "react";
import * as ReactDOM from "react-dom";
```

This is the [most futureproof way](https://www.reddit.com/r/reactjs/comments/iyehol/import_react_from_react_will_go_away_in_distant/) to import React. If you set `--allowSyntheticDefaultImports` (or add `"allowSyntheticDefaultImports": true`) in your `tsconfig.json` you can use more familiar imports:

```tsx
import React from "react";
import ReactDOM from "react-dom";
```

<details>

<summary>Explanation</summary>

Why `allowSyntheticDefaultImports` over `esModuleInterop`? [Daniel Rosenwasser](https://twitter.com/drosenwasser/status/1003097042653073408) has said that it's better for webpack/parcel. For more discussion check out <https://github.com/wmonk/create-react-app-typescript/issues/214>

You should also check [the new TypeScript docs for official descriptions between each compiler flag](https://www.typescriptlang.org/tsconfig#allowSyntheticDefaultImports)!

</details>

<!--END-SECTION:setup-->

# Section 2: Getting Started

<!--START-SECTION:function-components-->

## Function Components

These can be written as normal functions that take a `props` argument and return a JSX element.

```tsx
type AppProps = { message: string }; /* could also use interface */
const App = ({ message }: AppProps) => <div>{message}</div>;
```

<details>

<summary><b>What about `React.FC`/`React.FunctionComponent`/`React.VoidFunctionComponent`?</b></summary>

You can also write components with `React.FunctionComponent` (or the shorthand `React.FC` - they are the same):

```tsx
const App: React.FunctionComponent<{ message: string }> = ({ message }) => (
  <div>{message}</div>
);
```

Some differences from the "normal function" version:

- `React.FunctionComponent` is explicit about the return type, while the normal function version is implicit (or else needs additional annotation).

- It provides typechecking and autocomplete for static properties like `displayName`, `propTypes`, and `defaultProps`.

  - Note that there are some known issues using `defaultProps` with `React.FunctionComponent`. See [this issue for details](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/87). We maintain a separate `defaultProps` section you can also look up.

- It provides an implicit definition of `children` (see below) - however there are some issues with the implicit `children` type (e.g. [DefinitelyTyped#33006](https://github.com/DefinitelyTyped/DefinitelyTyped/issues/33006)), and it might be better to be explicit about components that consume `children`, anyway.

```tsx
const Title: React.FunctionComponent<{ title: string }> = ({
  children,
  title,
}) => <div title={title}>{children}</div>;
```

<details>
<summary>

Using `React.VoidFunctionComponent` or `React.VFC`

</summary>

As of [@types/react 16.9.48](https://github.com/DefinitelyTyped/DefinitelyTyped/pull/46643), you can also use `React.VoidFunctionComponent` or `React.VFC` type if you want to type `children` explicitly. This is an interim solution until `FunctionComponent` will accept no children by default (planned for `@types/react@^18.0.0`).

```ts
type Props = { foo: string };

// OK now, in future, error
const FunctionComponent: React.FunctionComponent<Props> = ({
  foo,
  children,
}: Props) => {
  return (
    <div>
      {foo} {children}
    </div>
  ); // OK
};

// Error now, in future, deprecated
const VoidFunctionComponent: React.VoidFunctionComponent<Props> = ({
  foo,
  children,
}) => {
  return (
    <div>
      {foo}
      {children}
    </div>
  );
};
```

</details>

- _In the future_, it may automatically mark props as `readonly`, though that's a moot point if the props object is destructured in the parameter list.

In most cases it makes very little difference which syntax is used, but you may prefer the more explicit nature of `React.FunctionComponent`.

</details>

<details>
<summary><b>Minor Pitfalls</b></summary>

These patterns are not supported:

**Conditional rendering**

```tsx
const MyConditionalComponent = ({ shouldRender = false }) =>
  shouldRender ? <div /> : false; // don't do this in JS either
const el = <MyConditionalComponent />; // throws an error
```

This is because due to limitations in the compiler, function components cannot return anything other than a JSX expression or `null`, otherwise it complains with a cryptic error message saying that the other type is not assignable to `Element`.

```tsx
const MyArrayComponent = () => Array(5).fill(<div />);
const el2 = <MyArrayComponent />; // throws an error
```

**Array.fill**

Unfortunately just annotating the function type will not help so if you really need to return other exotic types that React supports, you'd need to perform a type assertion:

```tsx
const MyArrayComponent = () => (Array(5).fill(<div />) as any) as JSX.Element;
```

[See commentary by @ferdaber here](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/57).

</details>

<!--END-SECTION:function-components-->

<!--START-SECTION:hooks-->

## Hooks

Hooks are [supported in `@types/react` from v16.8 up](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/a05cc538a42243c632f054e42eab483ebf1560ab/types/react/index.d.ts#L800-L1031).

## useState

Type inference works very well most of the time:

```tsx
const [val, toggle] = React.useState(false);
// `val` is inferred to be a boolean
// `toggle` only takes booleans
```

See also the [Using Inferred Types](https://react-typescript-cheatsheet.netlify.app/docs/basic/troubleshooting/types/#using-inferred-types) section if you need to use a complex type that you've relied on inference for.

However, many hooks are initialized with null-ish default values, and you may wonder how to provide types. Explicitly declare the type, and use a union type:

```tsx
const [user, setUser] = React.useState<IUser | null>(null);

// later...
setUser(newUser);
```

## useReducer

You can use [Discriminated Unions](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes-func.html#discriminated-unions) for reducer actions. Don't forget to define the return type of reducer, otherwise TypeScript will infer it.

```tsx
const initialState = { count: 0 };

type ACTIONTYPE =
  | { type: "increment"; payload: number }
  | { type: "decrement"; payload: string };

function reducer(state: typeof initialState, action: ACTIONTYPE) {
  switch (action.type) {
    case "increment":
      return { count: state.count + action.payload };
    case "decrement":
      return { count: state.count - Number(action.payload) };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = React.useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({ type: "decrement", payload: "5" })}>
        -
      </button>
      <button onClick={() => dispatch({ type: "increment", payload: 5 })}>
        +
      </button>
    </>
  );
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play?#code/LAKFEsFsAcHsCcAuACAVMghgZ2QJQKYYDGKAZvLJMgOTyEnUDcooRsAdliuO+IuBgA2AZUQZE+ZAF5kAbzYBXdogBcyAAwBfZmBCIAntEkBBAMIAVAJIB5AHLmAmgAUAotOShkyAD5zkBozVqHiI6SHxlagAaZGgMfUFYDAATNXYFSAAjfHhNDxAvX1l-Q3wg5PxQ-HDImLiEpNTkLngeAHM8ll1SJRJwDmQ6ZIUiHIAKLnEykqNYUmQePgERMQkY4n4ONTMrO0dXAEo5T2aAdz4iAAtkMY3+9gA6APwj2ROvImxJYPYqmsRqCp3l5BvhEAp4Ow5IplGpJhIHjCUABqTB9DgPeqJFLaYGfLDfCp-CIAoEFEFeOjgyHQ2BKVTNVb4RF05TIAC0yFsGWy8Fu6MeWMaB1x5K8FVIGAUglUwK8iEuFFOyHY+GVLngFD5Bx0Xk0oH13V6myhplZEm1x3JbE4KAA2vD8DFkuAsHFEFcALruAgbB4KAkEYajPlDEY5GKLfhCURTHUnKkQqFjYEAHgAfHLkGb6WpZI6WfTDRSvKnMgpEIgBhxTIJwEQANZSWRjI5SdPIF1u8RXMayZ7lSphEnRWLxbFNagAVmomhF6fZqYA9OXKxxM2KQWWK1WoTW643m63pB2u+7e-3SkEQsPamOGik1FO55p08jl6vdxuKcvv8h4yAmhAA)

<details>

<summary><b>Usage with `Reducer` from `redux`</b></summary>

In case you use the [redux](https://github.com/reduxjs/redux) library to write reducer function, It provides a convenient helper of the format `Reducer<State, Action>` which takes care of the return type for you.

So the above reducer example becomes:

```tsx
import { Reducer } from 'redux';

export function reducer: Reducer<AppState, Action>() {}
```

</details>

## useEffect

When using `useEffect`, take care not to return anything other than a function or `undefined`, otherwise both TypeScript and React will yell at you. This can be subtle when using arrow functions:

```ts
function DelayedEffect(props: { timerMs: number }) {
  const { timerMs } = props;

  useEffect(
    () =>
      setTimeout(() => {
        /* do stuff */
      }, timerMs),
    [timerMs]
  );
  // bad example! setTimeout implicitly returns a number
  // because the arrow function body isn't wrapped in curly braces
  return null;
}
```

<details>
<summary>
Solution to the above example
</summary>

```tsx
function DelayedEffect(props: { timerMs: number }) {
  const { timerMs } = props;

  useEffect(() => {
    setTimeout(() => {
      /* do stuff */
    }, timerMs);
  }, [timerMs]);
  // better; use the void keyword to make sure you return undefined
  return null;
}
```

</details>

## useRef

When using `useRef`, you have two options when creating a ref container that does not have an initial value:

```ts
const ref1 = useRef<HTMLElement>(null!);
const ref2 = useRef<HTMLElement | null>(null);
```

The first option will make `ref1.current` read-only, and is intended to be passed in to built-in `ref` attributes that React will manage (because React handles setting the `current` value for you).

<details>
  <summary>What is the <code>!</code> at the end of <code>null!</code>?</summary>

`null!` is a non-null assertion operator (the `!`). It asserts that any expression before it is not `null` or `undefined`, so if you have `useRef<HTMLElement>(null!)` it means that you're instantiating the ref with a current value of `null` but lying to TypeScript that it's not `null`.

```ts
function MyComponent() {
  const ref1 = useRef<HTMLElement>(null!);
  useEffect(() => {
    doSomethingWith(ref1.current);
    // TypeScript won't require null-check e.g. ref1 && ref1.current
  });
  return <div ref={ref1}> etc </div>;
}
```

</details>

The second option will make `ref2.current` mutable, and is intended for "instance variables" that you manage yourself.

```tsx
function TextInputWithFocusButton() {
  // initialise with null, but tell TypeScript we are looking for an HTMLInputElement
  const inputEl = React.useRef<HTMLInputElement>(null);
  const onButtonClick = () => {
    // strict null checks need us to check if inputEl and current exist.
    // but once current exists, it is of type HTMLInputElement, thus it
    // has the method focus! ✅
    if (inputEl && inputEl.current) {
      inputEl.current.focus();
    }
  };
  return (
    <>
      {/* in addition, inputEl only can be used with input elements. Yay! */}
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Focus the input</button>
    </>
  );
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgIilQ3wFgAoCzAVwDsNgJa4AVJADxgElaxqYA6sBgALAGIQ01AM4AhfjCYAKAJRwA3hThwA9DrjBaw4CgA2waUjgB3YSLi1qp0wBo4AI35wYSZ6wCeYEgAymhQwGDw1lYoRHCmEBAA1oYA5nCY0HAozAASLACyADI8fDAAoqZIIEi0MFpwaEzS8IZllXAAvIjEMAB0MkjImAA8+cWl-JXVtTAAfEqOzioA3A1NtC1wTPIwirQAwuZoSV1wql1zGg3aenAt4RgOTqaNIkgn0g5ISAAmcDJvBA3h9TsBMAZeFNXjl-lIoEQ6nAOBZ+jddPpPPAmGgrPDEfAUS1pG5hAYvhAITBAlZxiUoRUqjU6m5RIDhOi7iIUF9RFYaqIIP9MlJpABCOCAUHJ0eDzm1oXAAGSKyHtUx9fGzNSacjaPWq6Ea6gI2Z9EUyVRrXV6gC+DRtVu0RBgxuYSnRIzm6O06h0ACpIdlfr9jExSQyOkxTP5GjkPFZBv9bKIDYSmbNpH04ABNFD+CV+nR2636kby+BETCddTlyo27w0zr4HycfC6L0lvUjLH7baHY5Jas7BRMI7AE42uYSUXed6pkY6HtMDulnQruCrCg2oA)

example from [Stefan Baumgartner](https://fettblog.eu/typescript-react/hooks/#useref)

## useImperativeHandle

_we dont have much here, but this is from [a discussion in our issues](https://github.com/typescript-cheatsheets/react/issues/106). Please contribute if you have anything to add!_

```tsx
type ListProps<ItemType> = {
  items: ItemType[];
  innerRef?: React.Ref<{ scrollToItem(item: ItemType): void }>;
};

function List<ItemType>(props: ListProps<ItemType>) {
  useImperativeHandle(props.innerRef, () => ({
    scrollToItem() {},
  }));
  return null;
}
```

## Custom Hooks

If you are returning an array in your Custom Hook, you will want to avoid type inference as TypeScript will infer a union type (when you actually want different types in each position of the array). Instead, use [TS 3.4 const assertions](https://devblogs.microsoft.com/typescript/announcing-typescript-3-4/#const-assertions):

```tsx
export function useLoading() {
  const [isLoading, setState] = React.useState(false);
  const load = (aPromise: Promise<any>) => {
    setState(true);
    return aPromise.finally(() => setState(false));
  };
  return [isLoading, load] as const; // infers [boolean, typeof load] instead of (boolean | typeof load)[]
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?target=5&jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCpAD0ljkwFcA7DYCZuRgZyQBkIKACbBmAcwAUASjgBvCnDhoO3eAG1g3AcNFiANHF4wAyjBQwkAXTgBeRMRgA6HklPmkEzCgA2vKQG4FJRV4b0EhWzgJFAAFHBBNJAAuODjcRIAeFGYATwA+GRs8uSDFIzcLCRgoRiQA0rgiGEYoTlj4xMdMUR9vHIlpW2Lys0qvXzr68kUAX0DpxqRm1rgNLXDdAzDhaxRuYOZVfzgAehO4UUwkKH21ACMICG9UZgMYHLAkCEw4baFrUSqVARb5RB5PF5wAA+cHen1BfykaksFBmQA)

This way, when you destructure you actually get the right types based on destructure position.

<details>
<summary><b>Alternative: Asserting a tuple return type</b></summary>

If you are [having trouble with const assertions](https://github.com/babel/babel/issues/9800), you can also assert or define the function return types:

```tsx
export function useLoading() {
  const [isLoading, setState] = React.useState(false);
  const load = (aPromise: Promise<any>) => {
    setState(true);
    return aPromise.finally(() => setState(false));
  };
  return [isLoading, load] as [
    boolean,
    (aPromise: Promise<any>) => Promise<any>
  ];
}
```

A helper function that automatically types tuples can also be helpful if you write a lot of custom hooks:

```tsx
function tuplify<T extends any[]>(...elements: T) {
  return elements;
}

function useArray() {
  const numberValue = useRef(3).current;
  const functionValue = useRef(() => {}).current;
  return [numberValue, functionValue]; // type is (number | (() => void))[]
}

function useTuple() {
  const numberValue = useRef(3).current;
  const functionValue = useRef(() => {}).current;
  return tuplify(numberValue, functionValue); // type is [number, () => void]
}
```

</details>

Note that the React team recommends that custom hooks that return more than two values should use proper objects instead of tuples, however.

## More Hooks + TypeScript reading:

- https://medium.com/@jrwebdev/react-hooks-in-typescript-88fce7001d0d
- https://fettblog.eu/typescript-react/hooks/#useref

If you are writing a React Hooks library, don't forget that you should also expose your types for users to use.

## Example React Hooks + TypeScript Libraries:

- https://github.com/mweststrate/use-st8
- https://github.com/palmerhq/the-platform
- https://github.com/sw-yx/hooks

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:hooks-->

<!--START-SECTION:class-components-->

## Class Components

Within TypeScript, `React.Component` is a generic type (aka `React.Component<PropType, StateType>`), so you want to provide it with (optional) prop and state type parameters:

```tsx
type MyProps = {
  // using `interface` is also ok
  message: string;
};
type MyState = {
  count: number; // like this
};
class App extends React.Component<MyProps, MyState> {
  state: MyState = {
    // optional second annotation for better type inference
    count: 0,
  };
  render() {
    return (
      <div>
        {this.props.message} {this.state.count}
      </div>
    );
  }
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCmATzCTgFlqAFHMAZzgF44BvCuHAD0QuAFd2wAHYBzOAANpMJFEzok8uME4oANuwhwIAawFwQSduxQykALjjsYUaTIDcFAL4fyNOo2oAZRgUZW4+MzQIMSkYBykxEAAjFTdhUV1gY3oYAAttLx80XRQrOABBMDA4JAAPZSkAE05kdBgAOgBhXEgpJFiAHiZWCA4AGgDg0KQAPgjyQSdphyYpsJ5+BcF0ozAYYAgpPUckKKa4FCkpCBD9w7hMaDgUmGUoOD96aUwVfrQkMyCKIxOJwAAMZm8ZiITRUAAoAJTzbZwIgwMRQKRwOGA7YDRrAABuM1xKN4eW07TAbHY7QsVhsSE8fAptKWynawNinlJcAGQgJxNxCJ8gh55E8QA)

Don't forget that you can export/import/extend these types/interfaces for reuse.

<details>
<summary><b>Why annotate <code>state</code> twice?</b></summary>

It isn't strictly necessary to annotate the `state` class property, but it allows better type inference when accessing `this.state` and also initializing the state.

This is because they work in two different ways, the 2nd generic type parameter will allow `this.setState()` to work correctly, because that method comes from the base class, but initializing `state` inside the component overrides the base implementation so you have to make sure that you tell the compiler that you're not actually doing anything different.

[See commentary by @ferdaber here](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/57).

</details>

<details>
  <summary><b>No need for <code>readonly</code></b></summary>

You often see sample code include `readonly` to mark props and state immutable:

```tsx
type MyProps = {
  readonly message: string;
};
type MyState = {
  readonly count: number;
};
```

This is not necessary as `React.Component<P,S>` already marks them as immutable. ([See PR and discussion!](https://github.com/DefinitelyTyped/DefinitelyTyped/pull/26813))

</details>

**Class Methods**: Do it like normal, but just remember any arguments for your functions also need to be typed:

```tsx
class App extends React.Component<{ message: string }, { count: number }> {
  state = { count: 0 };
  render() {
    return (
      <div onClick={() => this.increment(1)}>
        {this.props.message} {this.state.count}
      </div>
    );
  }
  increment = (amt: number) => {
    // like this
    this.setState((state) => ({
      count: state.count + amt,
    }));
  };
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCtAGxQGc64BBMMOJADxiQDsATRsnQwAdAGFckHrxgAeAN5wQSBigDmSAFxw6MKMB5q4AXwA0cRWggBXHjG09rIAEZIoJgHwWKcHTBTccAC8FnBWtvZwAAwmANw+cET8bgAUAJTe5L6+RDDWUDxwKQnZcLJ8wABucBA8YtTAaADWQfLpwV4wABbAdCIGaETKdikAjGnGHiWlFt29ImA4YH3KqhrGsz19ugFIIuF2xtO+sgD0FZVTWdlp8ddH1wNDMsFFKCCRji5uGUFe8tNTqc4A0mkg4HM6NNISI6EgYABlfzcFI7QJ-IoA66lA6RNF7XFwADUcHeMGmxjStwSxjuxiAA)

**Class Properties**: If you need to declare class properties for later use, just declare it like `state`, but without assignment:

```tsx
class App extends React.Component<{
  message: string;
}> {
  pointer: number; // like this
  componentDidMount() {
    this.pointer = 3;
  }
  render() {
    return (
      <div>
        {this.props.message} and {this.pointer}
      </div>
    );
  }
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCtAGxQGc64BBMMOJADxiQDsATRsnQwAdAGFckHrxgAeAN4U4cEEgYoA5kgBccOjCjAeGgNwUAvgD44i8sshHuUXTwCuIAEZIoJuAHo-OGpgAGskOBgAC2A6JTg0SQhpHhgAEWA+AFkIVxSACgBKGzjlKJiRBxTvOABeOABmMzs4cziifm9C4ublIhhXKB44PJLlOFk+YAA3S1GxmzK6CpwwJdV1LXM4FH4F6KXKp1aesdk-SZnRgqblY-MgA)

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

## Typing getDerivedStateFromProps

Before you start using `getDerivedStateFromProps`, please go through the [documentation](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops) and [You Probably Don't Need Derived State](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html). Derived State can be implemented using hooks which can also help set up memoization.

Here are a few ways in which you can annotate `getDerivedStateFromProps`

1. If you have explicitly typed your derived state and want to make sure that the return value from `getDerivedStateFromProps` conforms to it.

```tsx
class Comp extends React.Component<Props, State> {
  static getDerivedStateFromProps(
    props: Props,
    state: State
  ): Partial<State> | null {
    //
  }
}
```

2. When you want the function's return value to determine your state.

```tsx
class Comp extends React.Component<
  Props,
  ReturnType<typeof Comp["getDerivedStateFromProps"]>
> {
  static getDerivedStateFromProps(props: Props) {}
}
```

3. When you want derived state with other state fields and memoization

```tsx
type CustomValue = any;
interface Props {
  propA: CustomValue;
}
interface DefinedState {
  otherStateField: string;
}
type State = DefinedState & ReturnType<typeof transformPropsToState>;
function transformPropsToState(props: Props) {
  return {
    savedPropA: props.propA, // save for memoization
    derivedState: props.propA,
  };
}
class Comp extends React.PureComponent<Props, State> {
  constructor(props: Props) {
    super(props);
    this.state = {
      otherStateField: "123",
      ...transformPropsToState(props),
    };
  }
  static getDerivedStateFromProps(props: Props, state: State) {
    if (isEqual(props.propA, state.savedPropA)) return null;
    return transformPropsToState(props);
  }
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoUSWOYAZwFEBHAVxQBs5tcD2IATFHQAWAOnpJWHMuQowAnmCRwAwizoxcANQ4tlAXjgoAdvIDcFYMZhIomdMoAKOMHTgBvCnDhgXAQQAuVXVNEB12PQtyAF9La1t7NGUAESRMKyR+AGUYFBsPLzgIGGFbHLykADFgJHZ+II0oKwBzKNjyBSU4cvzDVPTjTJ7lADJEJBgWKGMAFUUkAB5OpAhMOBgoEzpMaBBnCFcZiGGAPijMFmMMYAhjdc3jbd39w+PcmwAKXwO6IJe6ACUBXI3iIk2mwO83joKAAbpkXoEfC46KJvmA-AAaOAAehxcBh8K40DgICQIAgwAAXnkbsZCt5+LZgPDsu8kEF0aj0X5CtE2hQ0OwhG4VLgwHAkAAPGzGfhuZDoGCiRxTJBi8C3JDWBb-bGnSFwNC3RosDDQL4ov4ooGeEFQugsJRQS0-AFRKHrYT0UQaCpwQx2z3eYqlKDDaq1epwABEAEYAEwAZhjmIZUNEmY2Wx2UD2KKOw1drgB6f5fMKfpgwDQcGaE1STVZEZw+Z+xd+cD1BPZQWGtvTwDWH3ozDY7A7aP82KrSF9cIR-gBQLBUzuxhY7HYHqhq4h2ceubbryLXPdFZiQA)

<!--END-SECTION:class-components-->

<!--START-SECTION:default-props-->

## You May Not Need `defaultProps`

As per [this tweet](https://twitter.com/dan_abramov/status/1133878326358171650), defaultProps will eventually be deprecated. You can check the discussions here:

- https://twitter.com/hswolff/status/1133759319571345408

The consensus is to use object default values.

Function Components:

```tsx
type GreetProps = { age?: number };

const Greet = ({ age = 21 }: GreetProps) => // etc
```

Class Components:

```tsx
type GreetProps = {
  age?: number;
};

class Greet extends React.Component<GreetProps> {
  render() {
    const { age = 21 } = this.props;
    /*...*/
  }
}

let el = <Greet age={3} />;
```

## Typing `defaultProps`

Type inference improved greatly for `defaultProps` in [TypeScript 3.0+](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-0.html), although [some edge cases are still problematic](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/61).

**Function Components**

```tsx
type GreetProps = { age: number } & typeof defaultProps;
const defaultProps = {
  age: 21,
};

const Greet = (props: GreetProps) => {
  // etc
};
Greet.defaultProps = defaultProps;
```

_[See this in TS Playground](https://www.typescriptlang.org/play?#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcARFDvmQNwBQdMAnmFnAOKVYwAKxY6ALxwA3igDmWAFxwAdgFcQAIyxQ4AXzgAyOM1YQCcACZYCyeQBte-VPVwRZqeCbOXrEAXGEi6cCdLgAJgBGABo6dXo6e0d4TixuLzgACjAbGXjuPg9UAEovAD5RXzhKGHkoWTgAHiNgADcCkTScgDpkSTgAeiQFZVVELvVqrrrGiPpMmFaXcytsz2FZtwXbOiA)_

For **Class components**, there are [a couple ways to do it](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/pull/103#issuecomment-481061483)(including using the `Pick` utility type) but the recommendation is to "reverse" the props definition:

```tsx
type GreetProps = typeof Greet.defaultProps & {
  age: number;
};

class Greet extends React.Component<GreetProps> {
  static defaultProps = {
    age: 21,
  };
  /*...*/
}

// Type-checks! No type assertions needed!
let el = <Greet age={3} />;
```

<details>
  <summary>
  
   `JSX.LibraryManagedAttributes` nuance for library authors
   
   </summary>

The above implementations work fine for App creators, but sometimes you want to be able to export `GreetProps` so that others can consume it. The problem here is that the way `GreetProps` is defined, `age` is a required prop when it isn't because of `defaultProps`.

The insight to have here is that [`GreetProps` is the _internal_ contract for your component, not the _external_, consumer facing contract](https://github.com/typescript-cheatsheets/react/issues/66#issuecomment-453878710). You could create a separate type specifically for export, or you could make use of the `JSX.LibraryManagedAttributes` utility:

```tsx
// internal contract, should not be exported out
type GreetProps = {
  age?: number;
};

class Greet extends Component<GreetProps> {
  static defaultProps = { age: 21 };
}

// external contract
export type ApparentGreetProps = JSX.LibraryManagedAttributes<
  typeof Greet,
  GreetProps
>;
```

``This will work properly, although hovering over`ApparentGreetProps`may be a little intimidating. You can reduce this boilerplate with the`ComponentProps` utility detailed below.

</details>

## Consuming Props of a Component with defaultProps

A component with `defaultProps` may seem to have some required props that actually aren't.

### Problem Statement

Here's what you want to do:

```tsx
interface IProps {
  name: string;
}
const defaultProps = {
  age: 25,
};
const GreetComponent = ({ name, age }: IProps & typeof defaultProps) => (
  <div>{`Hello, my name is ${name}, ${age}`}</div>
);
GreetComponent.defaultProps = defaultProps;

const TestComponent = (props: React.ComponentProps<typeof GreetComponent>) => {
  return <h1 />;
};

// Property 'age' is missing in type '{ name: string; }' but required in type '{ age: number; }'
const el = <TestComponent name="foo" />;
```

### Solution

Define a utility that applies `JSX.LibraryManagedAttributes`:

```tsx
type ComponentProps<T> = T extends
  | React.ComponentType<infer P>
  | React.Component<infer P>
  ? JSX.LibraryManagedAttributes<T, P>
  : never;

const TestComponent = (props: ComponentProps<typeof GreetComponent>) => {
  return <h1 />;
};

// No error
const el = <TestComponent name="foo" />;
```

[_See this in TS Playground_](https://www.typescriptlang.org/play?#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcARFDvmQNwBQdMAnmFnAMImQB2W3MABWJhUAHgAqAPjgBeOOLhYAHjD4ATdNjwwAdJ3ARe-cSyyjg3AlihwB0gD6Yqu-Tz4xzl67cl04cAH44ACkAZQANHQAZYAAjKGQoJgBZZG5kAHMsNQBBGBgoOIBXVTFxABofPzgALjheADdrejoLVSgCPDYASSEIETgAb2r0kCw61AKLDPoAXzpcQ0m4NSxOooAbQWF0OWH-TPG4ACYAVnK6WfpF7mWAcUosGFdDd1k4AApB+uQxysO4LM6r0dnAAGRwZisCAEFZrZCbbb9VAASlk0g+1VEamADUkgwABgAJLAbDYQSogJg-MZwYDoAAkg1GWFmlSZh1mBNmogA9Di8XQUfQHlgni8jLpVustn0BnJpQjZTsWrzeXANsh2gwbstxFhJhK3nIPmAdnUjfw5WIoVgYXBReKuK9+JI0TJpPs4JQYEUoNw4KIABYARjgvN8VwYargADkIIooMQoAslvBSe8JAbns7JTSsDIyAQIBAyOHJDQgA)

## Misc Discussions and Knowledge

<details>
  <summary>Why does React.FC break defaultProps?</summary>

You can check the discussions here:

- https://medium.com/@martin_hotell/10-typescript-pro-tips-patterns-with-or-without-react-5799488d6680
- https://github.com/DefinitelyTyped/DefinitelyTyped/issues/30695
- https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/87

This is just the current state and may be fixed in future.

</details>

<details>
 <summary>TypeScript 2.9 and earlier</summary>

For TypeScript 2.9 and earlier, there's more than one way to do it, but this is the best advice we've yet seen:

```ts
type Props = Required<typeof MyComponent.defaultProps> & {
  /* additional props here */
};

export class MyComponent extends React.Component<Props> {
  static defaultProps = {
    foo: "foo",
  };
}
```

Our former recommendation used the `Partial type` feature in TypeScript, which means that the current interface will fulfill a partial version on the wrapped interface. In that way we can extend defaultProps without any changes in the types!

```ts
interface IMyComponentProps {
  firstProp?: string;
  secondProp: IPerson[];
}

export class MyComponent extends React.Component<IMyComponentProps> {
  public static defaultProps: Partial<IMyComponentProps> = {
    firstProp: "default",
  };
}
```

The problem with this approach is it causes complex issues with the type inference working with `JSX.LibraryManagedAttributes`. Basically it causes the compiler to think that when creating a JSX expression with that component, that all of its props are optional.

[See commentary by @ferdaber here](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/57) and [here](https://github.com/typescript-cheatsheets/react/issues/61).

</details>

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:default-props-->

<!--START-SECTION:type-or-interface-->

## Types or Interfaces?

`interface`s are different from `type`s in TypeScript, but they can be used for very similar things as far as common React uses cases are concerned. Here's a helpful rule of thumb:

- always use `interface` for public API's definition when authoring a library or 3rd party ambient type definitions, as this allows a consumer to extend them via _declaration merging_ if some definitions are missing.

- consider using `type` for your React Component Props and State, for consistency and because it is more constrained.

You can read more about the reasoning behind this rule of thumb in [Interface vs Type alias in TypeScript 2.7](https://medium.com/@martin_hotell/interface-vs-type-alias-in-typescript-2-7-2a8f1777af4c).

Types are useful for union types (e.g. `type MyType = TypeA | TypeB`) whereas Interfaces are better for declaring dictionary shapes and then `implementing` or `extending` them.

<details>
  <summary>
    <b>Useful table for Types vs Interfaces</b>
  </summary>
It's a nuanced topic, don't get too hung up on it. Here's a handy table:

| Aspect                                          | Type | Interface |
| ----------------------------------------------- | :--: | :-------: |
| Can describe functions                          |  ✅  |    ✅     |
| Can describe constructors                       |  ✅  |    ✅     |
| Can describe tuples                             |  ✅  |    ✅     |
| Interfaces can extend it                        |  ⚠️  |    ✅     |
| Classes can extend it                           |  🚫  |    ✅     |
| Classes can implement it (`implements`)         |  ⚠️  |    ✅     |
| Can intersect another one of its kind           |  ✅  |    ⚠️     |
| Can create a union with another one of its kind |  ✅  |    🚫     |
| Can be used to create mapped types              |  ✅  |    🚫     |
| Can be mapped over with mapped types            |  ✅  |    ✅     |
| Expands in error messages and logs              |  ✅  |    🚫     |
| Can be augmented                                |  🚫  |    ✅     |
| Can be recursive                                |  ⚠️  |    ✅     |

⚠️ In some cases

(source: [Karol Majewski](https://twitter.com/karoljmajewski/status/1082413696075382785))

</details>

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:type-or-interface-->

<!--START-SECTION:basic-type-examples-->

## Typing Component Props

This is intended as a basic orientation and reference for React developers familiarizing with TypeScript.

## Basic Prop Types Examples

A list of TypeScript types you will likely use in a React+TypeScript app:

```tsx
type AppProps = {
  message: string;
  count: number;
  disabled: boolean;
  /** array of a type! */
  names: string[];
  /** string literals to specify exact string values, with a union type to join them together */
  status: "waiting" | "success";
  /** any object as long as you dont use its properties (NOT COMMON but useful as placeholder) */
  obj: object;
  obj2: {}; // almost the same as `object`, exactly the same as `Object`
  /** an object with any number of properties (PREFERRED) */
  obj3: {
    id: string;
    title: string;
  };
  /** array of objects! (common) */
  objArr: {
    id: string;
    title: string;
  }[];
  /** a dict object with any number of properties of the same type */
  dict1: {
    [key: string]: MyTypeHere;
  };
  dict2: Record<string, MyTypeHere>; // equivalent to dict1
  /** any function as long as you don't invoke it (not recommended) */
  onSomething: Function;
  /** function that doesn't take or return anything (VERY COMMON) */
  onClick: () => void;
  /** function with named prop (VERY COMMON) */
  onChange: (id: number) => void;
  /** alternative function type syntax that takes an event (VERY COMMON) */
  onClick(event: React.MouseEvent<HTMLButtonElement>): void;
  /** an optional prop (VERY COMMON!) */
  optional?: OptionalType;
};
```

Notice we have used the TSDoc `/** comment */` style here on each prop. You can and are encouraged to leave descriptive comments on reusable components. For a fuller example and discussion, see our [Commenting Components](https://react-typescript-cheatsheet.netlify.app/docs/advanced/misc_concerns/#commenting-components) section in the Advanced Cheatsheet.

## Useful React Prop Type Examples

Relevant for components that accept other React components as props.

```tsx
export declare interface AppProps {
  children1: JSX.Element; // bad, doesnt account for arrays
  children2: JSX.Element | JSX.Element[]; // meh, doesn't accept strings
  children3: React.ReactChildren; // despite the name, not at all an appropriate type; it is a utility
  children4: React.ReactChild[]; // better
  children: React.ReactNode; // best, accepts everything
  functionChildren: (name: string) => React.ReactNode; // recommended function as a child render prop type
  style?: React.CSSProperties; // to pass through style props
  onChange?: React.FormEventHandler<HTMLInputElement>; // form events! the generic parameter is the type of event.target
  //  more info: https://react-typescript-cheatsheet.netlify.app/docs/advanced/patterns_by_usecase/#wrappingmirroring
  props: Props & React.ComponentPropsWithoutRef<"button">; // to impersonate all the props of a button element and explicitly not forwarding its ref
  props2: Props & React.ComponentPropsWithRef<MyButtonWithForwardRef>; // to impersonate all the props of MyButtonForwardedRef and explicitly forwarding its ref
}
```

<details>
 <summary><b>JSX.Element vs React.ReactNode?</b></summary>

Quote [@ferdaber](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/57): A more technical explanation is that a valid React node is not the same thing as what is returned by `React.createElement`. Regardless of what a component ends up rendering, `React.createElement` always returns an object, which is the `JSX.Element` interface, but `React.ReactNode` is the set of all possible return values of a component.

- `JSX.Element` -> Return value of `React.createElement`
- `React.ReactNode` -> Return value of a component

</details>

[More discussion: Where ReactNode does not overlap with JSX.Element](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/129)

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

## Types or Interfaces?

You can use either Types or Interfaces to type Props and State, so naturally the question arises - which do you use?

Here's a helpful rule of thumb:

- always use `interface` for public API's definition when authoring a library or 3rd party ambient type definitions, as this allows a consumer to extend them via _declaration merging_ if some definitions are missing.

- consider using `type` for your React Component Props and State, for consistency and because it is more constrained.

You can read more about the reasoning behind this rule of thumb in [Interface vs Type alias in TypeScript 2.7](https://medium.com/@martin_hotell/interface-vs-type-alias-in-typescript-2-7-2a8f1777af4c).

> Note: At scale, there are performance reasons to prefer interfaces ([see official Microsoft notes on this](https://github.com/microsoft/TypeScript/wiki/Performance#preferring-interfaces-over-intersections)) but [take this with a grain of salt](https://news.ycombinator.com/item?id=25201887)

Types are useful for union types (e.g. `type MyType = TypeA | TypeB`) whereas Interfaces are better for declaring dictionary shapes and then `implementing` or `extending` them.

### Useful table for Types vs Interfaces

It's a nuanced topic, don't get too hung up on it. Here's a handy table:

| Aspect                                          | Type | Interface |
| ----------------------------------------------- | :--: | :-------: |
| Can describe functions                          |  ✅  |    ✅     |
| Can describe constructors                       |  ✅  |    ✅     |
| Can describe tuples                             |  ✅  |    ✅     |
| Interfaces can extend it                        |  ⚠️  |    ✅     |
| Classes can extend it                           |  🚫  |    ✅     |
| Classes can implement it (`implements`)         |  ⚠️  |    ✅     |
| Can intersect another one of its kind           |  ✅  |    ⚠️     |
| Can create a union with another one of its kind |  ✅  |    🚫     |
| Can be used to create mapped types              |  ✅  |    🚫     |
| Can be mapped over with mapped types            |  ✅  |    ✅     |
| Expands in error messages and logs              |  ✅  |    🚫     |
| Can be augmented                                |  🚫  |    ✅     |
| Can be recursive                                |  ⚠️  |    ✅     |

⚠️ In some cases

(source: [Karol Majewski](https://twitter.com/karoljmajewski/status/1082413696075382785))

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:basic-type-examples-->

<!--START-SECTION:react-prop-type-examples-->

## Useful React Prop Type Examples

```tsx
export declare interface AppProps {
  children1: JSX.Element; // bad, doesnt account for arrays
  children2: JSX.Element | JSX.Element[]; // meh, doesn't accept strings
  children3: React.ReactChildren; // despite the name, not at all an appropriate type; it is a utility
  children4: React.ReactChild[]; // better
  children: React.ReactNode; // best, accepts everything
  functionChildren: (name: string) => React.ReactNode; // recommended function as a child render prop type
  style?: React.CSSProperties; // to pass through style props
  onChange?: React.FormEventHandler<HTMLInputElement>; // form events! the generic parameter is the type of event.target
  //  more info: https://react-typescript-cheatsheet.netlify.app/docs/advanced/patterns_by_usecase/#wrappingmirroring
  props: Props & React.ComponentPropsWithoutRef<"button">; // to impersonate all the props of a button element and explicitly not forwarding its ref
  props2: Props & React.ComponentPropsWithRef<MyButtonWithForwardRef>; // to impersonate all the props of MyButtonForwardedRef and explicitly forwarding its ref
}
```

<details>
 <summary><b>JSX.Element vs React.ReactNode?</b></summary>

Quote [@ferdaber](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/57): A more technical explanation is that a valid React node is not the same thing as what is returned by `React.createElement`. Regardless of what a component ends up rendering, `React.createElement` always returns an object, which is the `JSX.Element` interface, but `React.ReactNode` is the set of all possible return values of a component.

- `JSX.Element` -> Return value of `React.createElement`
- `React.ReactNode` -> Return value of a component

</details>

[More discussion: Where ReactNode does not overlap with JSX.Element](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/129)

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:react-prop-type-examples-->

<!--START-SECTION:get-derived-state-from-props-->

## getDerivedStateFromProps

Before you start using `getDerivedStateFromProps`, please go through the [documentation](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops) and [You Probably Don't Need Derived State](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html). Derived State can be easily achieved using hooks which can also help set up memoization easily.

Here are a few ways in which you can annotate `getDerivedStateFromProps`

1. If you have explicitly typed your derived state and want to make sure that the return value from `getDerivedStateFromProps` conforms to it.

```tsx
class Comp extends React.Component<Props, State> {
  static getDerivedStateFromProps(
    props: Props,
    state: State
  ): Partial<State> | null {
    //
  }
}
```

2. When you want the function's return value to determine your state.

```tsx
class Comp extends React.Component<
  Props,
  ReturnType<typeof Comp["getDerivedStateFromProps"]>
> {
  static getDerivedStateFromProps(props: Props) {}
}
```

3. When you want derived state with other state fields and memoization

```tsx
type CustomValue = any;
interface Props {
  propA: CustomValue;
}
interface DefinedState {
  otherStateField: string;
}
type State = DefinedState & ReturnType<typeof transformPropsToState>;
function transformPropsToState(props: Props) {
  return {
    savedPropA: props.propA, // save for memoization
    derivedState: props.propA,
  };
}
class Comp extends React.PureComponent<Props, State> {
  constructor(props: Props) {
    super(props);
    this.state = {
      otherStateField: "123",
      ...transformPropsToState(props),
    };
  }
  static getDerivedStateFromProps(props: Props, state: State) {
    if (isEqual(props.propA, state.savedPropA)) return null;
    return transformPropsToState(props);
  }
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoUSWOYAZwFEBHAVxQBs5tcD2IATFHQAWAOnpJWHMuQowAnmCRwAwizoxcANQ4tlAXjgoAdvIDcFYMZhIomdMoAKOMHTgBvCnDhgXAQQAuVXVNEB12PQtyAF9La1t7NGUAESRMKyR+AGUYFBsPLzgIGGFbHLykADFgJHZ+II0oKwBzKNjyBSU4cvzDVPTjTJ7lADJEJBgWKGMAFUUkAB5OpAhMOBgoEzpMaBBnCFcZiGGAPijMFmMMYAhjdc3jbd39w+PcmwAKXwO6IJe6ACUBXI3iIk2mwO83joKAAbpkXoEfC46KJvmA-AAaOAAehxcBh8K40DgICQIAgwAAXnkbsZCt5+LZgPDsu8kEF0aj0X5CtE2hQ0OwhG4VLgwHAkAAPGzGfhuZDoGCiRxTJBi8C3JDWBb-bGnSFwNC3RosDDQL4ov4ooGeEFQugsJRQS0-AFRKHrYT0UQaCpwQx2z3eYqlKDDaq1epwABEAEYAEwAZhjmIZUNEmY2Wx2UD2KKOw1drgB6f5fMKfpgwDQcGaE1STVZEZw+Z+xd+cD1BPZQWGtvTwDWH3ozDY7A7aP82KrSF9cIR-gBQLBUzuxhY7HYHqhq4h2ceubbryLXPdFZiQA)

<!--END-SECTION:get-derived-state-from-props-->

<!--START-SECTION:forms-and-events-->

## Forms and Events

If performance is not an issue (and it usually isn't!), inlining handlers is easiest as you can just use [type inference and contextual typing](https://www.typescriptlang.org/docs/handbook/type-inference.html#contextual-typing):

```tsx
const el = (
  <button
    onClick={(event) => {
      /* event will be correctly typed automatically! */
    }}
  />
);
```

But if you need to define your event handler separately, IDE tooling really comes in handy here, as the @type definitions come with a wealth of typing. Type what you are looking for and usually the autocomplete will help you out. Here is what it looks like for an `onChange` for a form event:

```tsx
type State = {
  text: string;
};
class App extends React.Component<Props, State> {
  state = {
    text: "",
  };

  // typing on RIGHT hand side of =
  onChange = (e: React.FormEvent<HTMLInputElement>): void => {
    this.setState({ text: e.currentTarget.value });
  };
  render() {
    return (
      <div>
        <input type="text" value={this.state.text} onChange={this.onChange} />
      </div>
    );
  }
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCtAGxQGc64BBMMOJADxiQDsATRsnQwAdAGFckHrxgAeCnDgBvAL4AaBcs2KA9Drg8IcMDjB1tcblwBccOjCjAeAcwDcmlRQB8W8ovso3HAAvL6KilYwtgBE0R7ulH5wepYAnmBOznAQPIgAkgDiABIAKnAAFij8dsB8SNmYIZo5YpUu9aEAFEi2QhgiAGLQIACiAG4ysqUAsgAyeTxgAK4wI9RIIDJeAJS2YxC1IT5KFjDlwHQidEgwAMowgUidSpacUewiaEtQRDwwJSgoM4biIxihqEt6iptglFCpYXBfnUoJ1tmFwkQYN9cp0LIpZHxgGMvHjwrInMt4DB0khgtFItE4GCIbSlGcLlcHtwRJEVNkeK0qsDgmzzpcWm1gXydCSkuE4LIdITiRYYR4KCogA)

Instead of typing the arguments and return values with `React.FormEvent<>` and `void`, you may alternatively apply types to the event handler itself (_contributed by @TomasHubelbauer_):

```tsx
  // typing on LEFT hand side of =
  onChange: React.ChangeEventHandler<HTMLInputElement> = (e) => {
    this.setState({text: e.currentTarget.value})
  }
```

<details>

<summary><b>Why two ways to do the same thing?</b></summary>

The first method uses an inferred method signature `(e: React.FormEvent<HTMLInputElement>): void` and the second method enforces a type of the delegate provided by `@types/react`. So `React.ChangeEventHandler<>` is simply a "blessed" typing by `@types/react`, whereas you can think of the inferred method as more... _artisanally hand-rolled_. Either way it's a good pattern to know. [See our Github PR for more](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/pull/24).

</details>

**Typing onSubmit, with Uncontrolled components in a Form**

If you don't quite care about the type of the event, you can just use React.SyntheticEvent. If your target form has custom named inputs that you'd like to access, you can use type widening:

```tsx
<form
  ref={formRef}
  onSubmit={(e: React.SyntheticEvent) => {
    e.preventDefault();
    const target = e.target as typeof e.target & {
      email: { value: string };
      password: { value: string };
    };
    const email = target.email.value; // typechecks!
    const password = target.password.value; // typechecks!
    // etc...
  }}
>
  <div>
    <label>
      Email:
      <input type="email" name="email" />
    </label>
  </div>
  <div>
    <label>
      Password:
      <input type="password" name="password" />
    </label>
  </div>
  <div>
    <input type="submit" value="Log in" />
  </div>
</form>
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCtCAOwGctoRlM4BeRYmAOgFc6kLABQBKClVoM4AMSbs4o9gD4FFOHAA8mJmrhFMbAN7aozJJgC+u2gGVeAIxDAYRoUgBcndDxsBPGjAAFkgwwGgAogBuSAEiynCGuupI3GBE0QEAIuYovAA2MKIA3Elw1PTwMChQAOYh8ilVtfUodHAwvmBIEKyN1XXwAGQJpckgKMB5noZwkSh5vB5wDFDANDVwFiXk6rtwYK10AO7QACbTs-OLnitrG1ulDzu75VJI45PyTQPc7xN53DmCyQRTgAHowe1Okg0ME0ABrOgAQlKr3gBzoxzOX36IVShxOUFOgKuIPBkI6XVhMMRKOe6ghcBCaG4rN0Fis5CUug0p2AkW59M0eRQ9iQeUFe3U4Q+U1GmjWYF4lWhbAARH9Jmq4DQUCAkOrNXltWDJbsNGCRWKJTywXyBTz7Wb1BoreLnbsAAoEs7ueUaRXKqFddUYrFE7W6-Whn0R8Eei1um3PC1Ox38hOBlUhtV0BxOGDaoGLdUAGQgGzWJrNqYzFAtJhAgpEQA)

Of course, if you're making any sort of significant form, [you should use Formik](https://jaredpalmer.com/formik) or [React Hook Form](https://react-hook-form.com/), which are written in TypeScript.

<!--END-SECTION:forms-and-events-->

<!--START-SECTION:context-->

## Context

## Basic Example

```tsx
import * as React from "react";

interface AppContextInterface {
  name: string;
  author: string;
  url: string;
}

const AppCtx = React.createContext<AppContextInterface | null>(null);

// Provider in your app

const sampleAppContext: AppContextInterface = {
  name: "Using React Context in a Typescript App",
  author: "thehappybug",
  url: "http://www.example.com",
};

export const App = () => (
  <AppCtx.Provider value={sampleAppContext}>...</AppCtx.Provider>
);

// Consume in your app

export const PostInfo = () => {
  const appContext = React.useContext(AppCtx);
  return (
    <div>
      Name: {appContext.name}, Author: {appContext.author}, Url:{" "}
      {appContext.url}
    </div>
  );
};
```

You can also use the [Class.contextType](https://reactjs.org/docs/context.html#classcontexttype) or [Context.Consumer](https://reactjs.org/docs/context.html#contextconsumer) API, let us know if you have trouble with that.

_[Thanks to @AlvSovereign](https://github.com/typescript-cheatsheets/react/issues/97)_

## Extended Example

Using `React.createContext` with an empty object as default value.

```tsx
interface ContextState {
  // set the type of state you want to handle with context e.g.
  name: string | null;
}
//set an empty object as default state
const Context = React.createContext({} as ContextState);
// set up context provider as you normally would in JavaScript [React Context API](https://reactjs.org/docs/context.html#api)
```

Using `React.createContext` and [context getters](https://kentcdodds.com/blog/application-state-management-with-react/) to make a `createCtx` with **no `defaultValue`, yet no need to check for `undefined`**:

```ts
import * as React from "react";

const currentUserContext = React.createContext<string | undefined>(undefined);

function EnthusasticGreeting() {
  const currentUser = React.useContext(currentUserContext);
  return <div>HELLO {currentUser!.toUpperCase()}!</div>;
}

function App() {
  return (
    <currentUserContext.Provider value="Anders">
      <EnthusasticGreeting />
    </currentUserContext.Provider>
  );
}
```

Notice the explicit type arguments which we need because we don't have a default `string` value:

```ts
const currentUserContext = React.createContext<string | undefined>(undefined);
//                                             ^^^^^^^^^^^^^^^^^^
```

along with the non-null assertion to tell TypeScript that `currentUser` is definitely going to be there:

```ts
return <div>HELLO {currentUser!.toUpperCase()}!</div>;
//                              ^
```

This is unfortunate because _we know_ that later in our app, a `Provider` is going to fill in the context.

There are a few solutions for this:

1. You can get around this by asserting non null:

   ```ts
   const currentUserContext = React.createContext<string>(undefined!);
   ```

   ([Playground here](https://www.typescriptlang.org/play/index.html?jsx=1#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcARFDvmQNwBQduEAdqvLgK5SXMwCqqLFADCLGFgAe8ALyYqMAHS5KycaN6SYAHjZRgzAOYA+ABQdmAEywF9WCwEIAlPQLn8wFnACivABYdUNBhgXABxSixgwxNHOABvOjg4JlZ2Lh5+QSg4WWw8RQCsdXEpE05uLF4BIWLNZ0S4ShguZjgtC2AANyMACS8AGX6AeXjyjOqoBRgIPjAwGrQsGIBfey0Aeg7u+mW6V2Z3TwBBOZj4hqaWtrHKzJqxTQUABWJO4CtszuQAGw4saTIAGVfMgAO7MMhGBpJLQ+GD+QJsELhLCRfQGODrKEw9Y3KpZWpSZ6vd5CIw7IA)) This is a quick and easy fix, but this loses type-safety, and if you forget to supply a value to the Provider, you will get an error.

2. We can write a helper function called `createCtx` that guards against accessing a `Context` whose value wasn't provided. By doing this, API instead, **we never have to provide a default and never have to check for `undefined`**:

   ```tsx
   import * as React from "react";

   /**
    * A helper to create a Context and Provider with no upfront default value, and
    * without having to check for undefined all the time.
    */
   function createCtx<A extends {} | null>() {
     const ctx = React.createContext<A | undefined>(undefined);
     function useCtx() {
       const c = React.useContext(ctx);
       if (c === undefined)
         throw new Error("useCtx must be inside a Provider with a value");
       return c;
     }
     return [useCtx, ctx.Provider] as const; // 'as const' makes TypeScript infer a tuple
   }

   // Usage:

   // We still have to specify a type, but no default!
   export const [useCurrentUserName, CurrentUserProvider] = createCtx<string>();

   function EnthusasticGreeting() {
     const currentUser = useCurrentUserName();
     return <div>HELLO {currentUser.toUpperCase()}!</div>;
   }

   function App() {
     return (
       <CurrentUserProvider value="Anders">
         <EnthusasticGreeting />
       </CurrentUserProvider>
     );
   }
   ```

   [View in the TypeScript Playground](http://www.typescriptlang.org/play/index.html?jsx=1&ssl=1&ssc=1&pln=31&pc=2#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcARFDvmQNwBQdA9AgnYnAIJwAWWANmCxQ4MCHFyVkMLCjgBhCADtpAD3jJFAEzgAFYgDdgmoXADuwGNziKxAVzBEl8YwWS2+8fcj62sAGhQtNiRzSwhbeG5kQ0UAcxExXF5cAGs4Amg4Wy0sAmBFLG1vPhFeEVAsADpgxjoCbPxgJXFJaTkYFQAeLiw1LC10AG8AXzgAH2t3PgA+AAoASjhBtnElVHh8FTgAXkwqGEqJHDanXphu8aycvILNOeyXfML5+jh0hpgmxSzULHaVBZLFZvXBrDY7PZ4A62X4KZRnWabF7AuDAAhwRE7ba7B65J6aRaWYimaxYEkAUSgxCgszIML+HTgIBh8AARjJ8qgjDJkLoDNzhKErLyvD4sGRkW83pQYLYoN9cK84MMVjK5d8ANr0-4BTaVPQQQzGKAAXRQ6FBinWNDgjEYcAA5GhVlaYA6mcgUlh0AAVACeggAyhJgGB4PkCCZebKwHwsHQVUx7QBVVDIWJYABcDDtcAA6jJ1sA+CUovoZKI4KhBLg0X7ZDAA-44KyItYxC43B4AIR0XqQWAu9ZwLWwuWUZSpoQAOWQIGbcnH-RgU6gBqNQjNuyOUgZXXWUHysTmyLqHy+cHJym4MLQn1wAHFKFhPnFAcsQWDxEvJ79hDixypZdV1necFiVNV5TgTpNGAfRpgACXJAAZZCAHkllwH8Vz-SpRGTMBBCgOQ0CwBZhm7TpGFg+D6ETepFEaZoOEI99VRfdVoMXIDfyEdcBTgUVfG2MhAyiUxFDIaYUU6K9LFvItH2fV94kYaS3io7iJxwvj+WNaY6KAA)

3. You can go even further and combine this idea using `React.createContext` and [context getters](https://kentcdodds.com/blog/application-state-management-with-react/).

   ```tsx
   /**
    * A helper to create a Context and Provider with no upfront default value, and
    * without having to check for undefined all the time.
    */
   function createCtx<A extends {} | null>() {
     const ctx = React.createContext<A | undefined>(undefined);
     function useCtx() {
       const c = React.useContext(ctx);
       if (c === undefined)
         throw new Error("useCtx must be inside a Provider with a value");
       return c;
     }
     return [useCtx, ctx.Provider] as const; // 'as const' makes TypeScript infer a tuple
   }

   // usage

   export const [useCtx, SettingProvider] = createCtx<string>(); // specify type, but no need to specify value upfront!
   export function App() {
     const key = useCustomHook("key"); // get a value from a hook, must be in a component
     return (
       <SettingProvider value={key}>
         <Component />
       </SettingProvider>
     );
   }
   export function Component() {
     const key = useCtx(); // can still use without null check!
     return <div>{key}</div>;
   }
   ```

   [View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCtCAOwGd4BXOpAYWZlwAkIIBrOAF44ACj5IAngC44DKMBoBzAJRCAfHADeFOHGr14AbQYoYSADSykMAMoxTSALpDExGADpmSOw5GaAvso6cEQwjFA0svZmhuISjhT+FAD0yXpEDnq0ZgAe8ADuwDAAFnA0EHCMYNjZcAAmSJgojAA2MABqKC2MSClphSUQjPDFKABuCopwnPUVjDQNmApIdXrFSGgCXS3T69OgveSY8xjAtOmoZqwwOQA8AIJqIqra5Lr6DHo3LsjoHmgZK7ZJB5B5wAA+lQWjWWdSe80WsOUAG5gscaKdzl5rjlnlpgu9aJ80D83J4WKxgXkRBgciiCXBgJhRABCNCqEo4fJlJDcgCiUBwUBEACJsd8QBw4AAjJCM+jABpwFBwAAKOAmDSgcAGpRVYy6PRF9LeuhC1nCkTQqNNSVNoUtcEM4pyllp7nVEE1SCgzhQdCyBmRcFScBAKHEcAAKhIwN4AcAwPAFJgfcrplUWhYyhB4ChIihBSgJHAIMz5mdIjBY0g6IkKH1KnQUIpDhQQZBYIHPs6KTdLDZrDBJp7vb6XADLmwbrc5JMniiQ2k6HG0EyS9W45ZpcMczyVtMKiuNuu4AbunKqjUaDAWe2cp2sCdh+d7mAwHjXoSDHA4i5sRw3C8HwopxMawahq2eZnoaco1HgKrFMBliSp8sryum1DgLQSA3sEDoRKIDK3IOMDDkoo6Kmm549IImhxP4agMrotyUthNC4fAyRMaaLHJKR5GKJRWo8boJp2h20BPhiL6RGxkAcTen7BB88B-sILrPBBaRoPmUTAC0OxeDqRRIbuNCtDsaDrJsd72hahG3HUwBjGo9GSP4tzJM5rk2v4QA)

4. Using `React.createContext` and `useContext` to make a `createCtx` with [`unstated`](https://github.com/jamiebuilds/unstated)-like context setters:

   ```tsx
   export function createCtx<A>(defaultValue: A) {
     type UpdateType = React.Dispatch<
       React.SetStateAction<typeof defaultValue>
     >;
     const defaultUpdate: UpdateType = () => defaultValue;
     const ctx = React.createContext({
       state: defaultValue,
       update: defaultUpdate,
     });
     function Provider(props: React.PropsWithChildren<{}>) {
       const [state, update] = React.useState(defaultValue);
       return <ctx.Provider value={{ state, update }} {...props} />;
     }
     return [ctx, Provider] as const; // alternatively, [typeof ctx, typeof Provider]
   }

   // usage

   const [ctx, TextProvider] = createCtx("someText");
   export const TextContext = ctx;
   export function App() {
     return (
       <TextProvider>
         <Component />
       </TextProvider>
     );
   }
   export function Component() {
     const { state, update } = React.useContext(TextContext);
     return (
       <label>
         {state}
         <input type="text" onChange={(e) => update(e.target.value)} />
       </label>
     );
   }
   ```

   [View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCpAD0ljkwFcA7DYCZuNIlGJAYRjUAPAEEAfAAoAJkkwpGAGxgA1FIsZIAXHFEBKOAG8KcODACeYJHACqYabyQAVS9YC8iYjAB0AEWAAzmC8aAAWwsjoPgDKSDDRMI6ibBzCFlYQmHCy8kqq6pri4gDcJlwcAfA5Csp2Dnw6dY4uVnAekgZu4tlyNfkaSKXkpmgV8BjUbZ5R3tyofPwcfNQwksbDpnCVjjrVeWoDADRlpoz2Oz25ted8ZQC+ekOmTKww7JwACjgAbsCyUJIwDgwAEdJEMN4vhAQQB1YAwUL8ULARTSIjMYSGO7iAzrTblZiVOAAbW2fEOcDO9SQAF0puCfIwAkgEo4ZL19gUkI8TnAiDBGFBOMIJpCfn8kFA4N8uW5DIYtolyZSbtY7ncjN4tUDoQENQB6Er3Mr8wWcYkTClQ37-OkoAIEyrFOD6-VwdR8IW8YDfJCKcwU4npJCZLhCCnB0PWiVQGkUO4UCiuykBFAAcyQifIo0J8At4bgThoMGjtqmc0cgmokgARAFcM5izWeeQaHRxmNC8XFsxlvAPBMhm3oFgWClOKIwGAOkYTXEzXBJLzhEWVqXJeJeaZhItwBwkL2XZuNtv9auS+L-sfTC2E63aCOGGO3hw4LvIMwD6tcWUc0SFWSSAUlSjhwBqHgMt4TICEsxaSOePZ9i2pimkKi7LooKAAEZ+te+JGIBd74XAwjAMwYCMPAwZuDWfY1nAHBIigzAZnK7jdCBfCSEg3iJFAGY+DKAx6AaeGnphOGKHht5AA)

5. A [useReducer-based version](https://gist.github.com/sw-yx/f18fe6dd4c43fddb3a4971e80114a052) may also be helpful.

<details>

<summary><b>Mutable Context Using a Class component wrapper</b></summary>

_Contributed by: [@jpavon](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/pull/13)_

```tsx
interface ProviderState {
  themeColor: string;
}

interface UpdateStateArg {
  key: keyof ProviderState;
  value: string;
}

interface ProviderStore {
  state: ProviderState;
  update: (arg: UpdateStateArg) => void;
}

const Context = React.createContext({} as ProviderStore); // type assertion on empty object

class Provider extends React.Component<{}, ProviderState> {
  public readonly state = {
    themeColor: "red",
  };

  private update = ({ key, value }: UpdateStateArg) => {
    this.setState({ [key]: value });
  };

  public render() {
    const store: ProviderStore = {
      state: this.state,
      update: this.update,
    };

    return (
      <Context.Provider value={store}>{this.props.children}</Context.Provider>
    );
  }
}

const Consumer = Context.Consumer;
```

</details>

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:context-->

<!--START-SECTION:forward-create-ref-->

## forwardRef/createRef

Check the [Hooks section](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/blob/master/README.md#hooks) for `useRef`.

`createRef`:

```tsx
class CssThemeProvider extends React.PureComponent<Props> {
  private rootRef = React.createRef<HTMLDivElement>(); // like this
  render() {
    return <div ref={this.rootRef}>{this.props.children}</div>;
  }
}
```

`forwardRef`:

```tsx
type Props = { children: React.ReactNode; type: "submit" | "button" };
export type Ref = HTMLButtonElement;
export const FancyButton = React.forwardRef<Ref, Props>((props, ref) => (
  <button ref={ref} className="MyClassName" type={props.type}>
    {props.children}
  </button>
));
```

<details>
  <summary>
    
    Side note: the `ref` you get from `forwardRef` is mutable so you can assign to it if needed.
    
  </summary>

This was done [on purpose](https://github.com/DefinitelyTyped/DefinitelyTyped/pull/43265/). You can make it immutable if you have to - assign `React.Ref` if you want to ensure nobody reassigns it:

```tsx
type Props = { children: React.ReactNode; type: "submit" | "button" };
export type Ref = HTMLButtonElement;
export const FancyButton = React.forwardRef((
  props: Props,
  ref: React.Ref<Ref> // <-- here!
) => (
  <button ref={ref} className="MyClassName" type={props.type}>
    {props.children}
  </button>
));
```

</details>

If you are grabbing the props of a component that forwards refs, use [`ComponentPropsWithRef`](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/a05cc538a42243c632f054e42eab483ebf1560ab/types/react/index.d.ts#L770).

More info: https://medium.com/@martin_hotell/react-refs-with-typescript-a32d56c4d315

You may also wish to do [Conditional Rendering with `forwardRef`](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/167).

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:forward-create-ref-->

<!--START-SECTION:portals-->

## Portals

Using `ReactDOM.createPortal`:

```tsx
const modalRoot = document.getElementById("modal-root") as HTMLElement;
// assuming in your html file has a div with id 'modal-root';

export class Modal extends React.Component {
  el: HTMLElement = document.createElement("div");

  componentDidMount() {
    modalRoot.appendChild(this.el);
  }

  componentWillUnmount() {
    modalRoot.removeChild(this.el);
  }

  render() {
    return ReactDOM.createPortal(this.props.children, this.el);
  }
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoUSWRYmAEQHkBZObXAo9GAWgBNcZchTQQAdgGd4ICHxQAbBBAjwAvHAFoAriCRiYAOgDmSGAFF5SXfoBCATwCSfABQAiGXPk8cK1wEo4FAk4AAkAFWYAGQsrPRgAbgoAeiTAiQkdYDEjOCy4OwgtKDgACxgQeTZgS1KgwI1gADc4AHdgGBLcvgIPBW9lGHxE4XIkAA9qeDR5IODmWQU4cZg9PmDkbgMAYVxIMTi4AG8KOCX5AC5QiOjLazUNCG07gzQuFZi7tz4m-2GTuFE4HEcXowD48y0+mcAWO5FOp16igGBhQYDAqy2JWqLg6wAkBiQ8j8w1OAF8KP9AXs4gB1aryACqYhkkJg0KO-wRCyRKgMRBkjSQmOxzlx+MJxP+5JGpyIYj4SCg7Nh8LgRBgRTEtG4TGYLzeSAACtAYApRVj8WAcGB8WgsfI+HKADRwMUEokkuDS0lAA)

<details>
  <summary><b>Using hooks</b></summary>

Same as above but using hooks

```tsx
import React, { useEffect, useRef } from "react";
import { createPortal } from "react-dom";

const modalRoot = document.querySelector("#modal-root") as HTMLElement;

const Modal: React.FC<{}> = ({ children }) => {
  const el = useRef(document.createElement("div"));

  useEffect(() => {
    // We assume `modalRoot` exists with '!'
    modalRoot!.appendChild(el.current);
    return () => void modalRoot!.removeChild(el.current);
  }, []);

  return createPortal(children, el.current);
};

export default Modal;
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play?#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoUSWOAbzjSJRiQAVoYUAbOAXzmy4CTDAFoAJrjLkKAellwUAZyUBXEMAB2Aczha4ATwiqocABYwQPTMC5JzyxXHHAAbnADuwGGb3iCIBDi3KI4EDD4ANwUFGgQmkrwALJB3ABciMQwAHQAYgDCADy0vAB8cAC8cAAU9GhmtuJEmnwAlJXltBRwcPJwAKIgqlzM9j72aCMqDLiQmkiaEUp6CZyaaPauKFDAKABGdp7evihwRJjdM6twSDxVyOg5qkpIyJjVkmjqCzmMqCz9OwgH7VABELlcoNarWiMnIPQeGGyzyQ-UwmCQGGq1XaFU6lx6fQA6vZlGpgXAAAaBYJcBAQcKUm4AD2AiWWXh8BAAhNIej04tcadx6eFKs4IF9gYtsgBHVRIKAGADKt0xMGgYIAxMKuKEGTAoYplgAJAAqSQAMoCkNKYLD+XBdaKYNzsigwGAFuJ8g0uOJqrdsl8oM0YDCCWckDATC0cR04K4IMB-M6DW6iIFXEhfY1A1xgyYwxH4XwADRwADaAF0S5c+gBJVaofwQTBU26UivjK6cLSKvTLHuU86F0M-SmXIgxqAtP6jdiwbjVeqNZoVoMh4uw3iwuQKZ4obRIGLkTCqdYwYDxOAAQU98a6pcFiSrSjMEA8KVpFZeMGVH5fqkXDVuKiJPC8yqcCw1SYNwLwlj006xjUkaFBCpSRoSChGKoDAoC08EQHAYCqPAPhsishjGKYiTMMAaDmJY1i2CepaOuhbh+BUoK6vq4SgqUhSyBhWF0O+n7ftwcAAGQyah7GOnAhRSVwmGKUpykQmJmmJAYdgVLQT6aSZzhsmAIwGBkoLaDs4igmWOkmRZ6BIA2LAgEo1kbIsioOU5mlmEgwDaBY1kAIwAAyRa4Zj+RpplHOIPgZPgUUxWY+COQlpl7OgADWtnGJo4jWVA2h5dUkVltVtXZOFrTxYlSkAF5NuISDMhkACc3XZc1PS8LwAVwOpA1wA2+B4KcurcrQoJwKCw05UphR7GRGotHpBlGXlaCFTgF6lYtYAegYKAeA0YBLfw8T5FwDH5YZ8Z4nAf4AZJwGwfBSCtGUkwQC8wnrTAm1jYlwmiStwmqeDjp-WJa0bTed0Pftz24uU72Aap1QwFACp-aUEkeHAqnA8jmhw-yfREK+bbUSYiiemhIluODrQULwQA)

</details>

Modal Component Usage Example:

```tsx
function App() {
  const [showModal, setShowModal] = React.useState(false);
  return (
    <div>
      // you can also put this in your static html file
      <div id="modal-root"></div>
      {showModal && (
        <Modal>
          <div
            style={{
              display: "grid",
              placeItems: "center",
              height: "100vh",
              width: "100vh",
              background: "rgba(0,0,0,0.1)",
              zIndex: 99,
            }}
          >
            I'm a modal!{" "}
            <button
              style={{ background: "papyawhip" }}
              onClick={() => setShowModal(false)}
            >
              close
            </button>
          </div>
        </Modal>
      )}
      <button onClick={() => setShowModal(true)}>show Modal</button>
      // rest of your app
    </div>
  );
}
```

<details>

<summary><b>Context of Example</b></summary>

This example is based on the [Event Bubbling Through Portal](https://reactjs.org/docs/portals.html#event-bubbling-through-portals) example of React docs.

</details>

<!--END-SECTION:portals-->

<!--START-SECTION:error-boundaries-->

## Error Boundaries

### Option 1: Using react-error-boundary

[React-error-boundary](https://github.com/bvaughn/react-error-boundary) - is a lightweight package ready to use for this scenario with TS support built-in.
This approach also lets you avoid class components that are not that popular anymore.

### Options 2: Writing your custom error boundary component

If you don't want to add a new npm package for this, you can also write your own `ErrorBoundary` component.

```jsx
import React, { Component, ErrorInfo, ReactNode } from "react";

interface Props {
  children: ReactNode;
}

interface State {
  hasError: boolean;
}

class ErrorBoundary extends Component<Props, State> {
  public state: State = {
    hasError: false
  };

  public static getDerivedStateFromError(_: Error): State {
    // Update state so the next render will show the fallback UI.
    return { hasError: true };
  }

  public componentDidCatch(error: Error, errorInfo: ErrorInfo) {
    console.error("Uncaught error:", error, errorInfo);
  }

  public render() {
    if (this.state.hasError) {
      return <h1>Sorry.. there was an error</h1>;
    }

    return this.props.children;
  }
}

export default ErrorBoundary;

```

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:error-boundaries-->

<!--START-SECTION:concurrent-->

## Concurrent React/React Suspense

_Not written yet._ watch <https://github.com/sw-yx/fresh-async-react> for more on React Suspense and Time Slicing.

[Something to add? File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:concurrent-->

<!--START-SECTION:types-->

# Troubleshooting Handbook: Types

> ⚠️ Have you read [the TypeScript FAQ](https://github.com/microsoft/TypeScript/wiki/FAQ?) Your answer might be there!

Facing weird type errors? You aren't alone. This is the hardest part of using TypeScript with React. Be patient - you are learning a new language after all. However, the more you get good at this, the less time you'll be working _against_ the compiler and the more the compiler will be working _for_ you!

Try to avoid typing with `any` as much as possible to experience the full benefits of TypeScript. Instead, let's try to be familiar with some of the common strategies to solve these issues.

## Union Types and Type Guarding

Union types are handy for solving some of these typing problems:

```tsx
class App extends React.Component<
  {},
  {
    count: number | null; // like this
  }
> {
  state = {
    count: null,
  };
  render() {
    return <div onClick={() => this.increment(1)}>{this.state.count}</div>;
  }
  increment = (amt: number) => {
    this.setState((state) => ({
      count: (state.count || 0) + amt,
    }));
  };
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCtAGxQGc64BBMMOJADxiQDsATRsnQwAdAGFckHrxgAeCnDgBvAL4AaBcs2K0EAK48YALjg89IAEZIocAD6m91agG44AejdxqwANZI4MAAWwHSaKhQAfFrkinQwKNxwALzRijr6hiZmTmHOmkT81gAUAJSpaUQwelA8cLJ8wABucBA8Yt5oPklKpclRQSEiwDxoRCAyRQCMJSoRSgN0InEJSCK6BjAqsm4NjRF5MXDhh8OjSOOGyXBFKCDGDpbWZUlRStoBwYt0SDAAyvHcIrLRIva5vQ5pODrTLXYGraHwWz2AAMZQA1HBbjB3ioSiUDooVAcVEA)

**Type Guarding**: Sometimes Union Types solve a problem in one area but create another downstream. If `A` and `B` are both object types, `A | B` isn't "either A or B", it is "A or B or both at once", which causes some confusion if you expected it to be the former. Learn how to write checks, guards, and assertions (also see the Conditional Rendering section below). For example:

```ts
interface Admin {
  role: string;
}
interface User {
  email: string;
}

// Method 1: use `in` keyword
function redirect(user: Admin | User) {
  if ("role" in user) {
    // use the `in` operator for typeguards since TS 2.7+
    routeToAdminPage(user.role);
  } else {
    routeToHomePage(user.email);
  }
}

// Method 2: custom type guard, does the same thing in older TS versions or where `in` isnt enough
function isAdmin(user: Admin | User): user is Admin {
  return (user as any).role !== undefined;
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoC4AOxiSk3STgEEATEGuAbwrjhwAbJAC44AZxhQaAcwDcFAL5Va9RmmYBVcfR584SECmCCxk6dXlKKFTAFdqGYBGoCIdugBUI7TtQAKKDJIABTiwDLUwJjA9ACUeuT80XBhEVExugC8OQR2OlAIEML4CbxJ-AJIMHZQrvi+NGQVinDWlOT2jjDOrjgeSN4AErhIgcFpkdGxUGX6KZMZM3A5WQSGxoKliZVVNXUEIyBIYEFIzfzK5FcUAPS3cACy1QAWEGxwAIxi+cwABjQ-nAANZIACeAHdoGxbA4nC4qmxgEQMCFflAxI1XAAfODaeI7ODREIAIiESBJRNc6LKcHucF+cBgL3+gLgEDA9BQMGgcEwvJgYM5MjsKCgbHEEhoGjgngAynAAEwAOgA7ABqfT8fpeHwcGjjULo5XkuIKFoGQQ6Qna9y6o5jM5ogrKjYmM36K43cj057M95KsRofI8vCCzlwEVitgAGjgbAgSElzOY4hQxyZL1kVPZgjYunlcAAbvRwi5JbyISyiHAAdQgcBxLQDNR3DIXrDur0ieIsc76Jj9Ti8QU4j8Cj3WEPCUR9q5+1A4ChJShqGC4ibiswAIS5Bz5mLUJAw65AA)

Method 2 is also known as [User-Defined Type Guards](https://www.typescriptlang.org/docs/handbook/advanced-types.html#user-defined-type-guards) and can be really handy for readable code. This is how TS itself refines types with `typeof` and `instanceof`.

If you need `if...else` chains or the `switch` statement instead, it should "just work", but look up [Discriminated Unions](https://www.typescriptlang.org/docs/handbook/advanced-types.html#discriminated-unions) if you need help. (See also: [Basarat's writeup](https://basarat.gitbook.io/typescript/type-system/discriminated-unions)). This is handy in typing reducers for `useReducer` or Redux.

## Optional Types

If a component has an optional prop, add a question mark and assign during destructure (or use defaultProps).

```tsx
class MyComponent extends React.Component<{
  message?: string; // like this
}> {
  render() {
    const { message = "default" } = this.props;
    return <div>{message}</div>;
  }
}
```

You can also use a `!` character to assert that something is not undefined, but this is not encouraged.

_Something to add? [File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new) with your suggestions!_

## Enum Types

Enums in TypeScript default to numbers. You will usually want to use them as strings instead:

```tsx
export enum ButtonSizes {
  default = "default",
  small = "small",
  large = "large",
}
```

Usage:

```tsx
export const PrimaryButton = (
  props: Props & React.HTMLProps<HTMLButtonElement>
) => <Button size={ButtonSizes.default} {...props} />;
```

A simpler alternative to enum is just declaring a bunch of strings with union:

```tsx
export declare type Position = "left" | "right" | "top" | "bottom";
```

This is handy because TypeScript will throw errors when you mistype a string for your props.

## Type Assertion

Sometimes you know better than TypeScript that the type you're using is narrower than it thinks, or union types need to be asserted to a more specific type to work with other APIs, so assert with the `as` keyword. This tells the compiler you know better than it does.

```tsx
class MyComponent extends React.Component<{
  message: string;
}> {
  render() {
    const { message } = this.props;
    return (
      <Component2 message={message as SpecialMessageType}>{message}</Component2>
    );
  }
}
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCmATzCTgGU61gUAbAWSQGduUBzJABVa9ALwFuMKMAB2-fAG4KFOTCRRM6egAUcYbnADeFOHBA8+ggFxwpM+XAA+cAK6yAJkkxykH5eQAvirkaBCyUnAAwriQskiyMABMtsjoMAB0AGJRADx6EAYAfHASABRG5pYCSIEAlKUlZaZwuR7AAG5FLWa5ABYAjEVGFrw1gbkA9IPd5L2T7V0UdSFobCi8cBzUMeDhCfBIAB7qnoZpGBm7cQe5JnNVYzZ20nL8AYEl92ZEnhplDW+ZjgYQi8Eqoys9ECpTgMD6wG4GTA+m4AWBcCIMFcUFkcGaDwxuWu+0SSUeULEI2qgjgG0YzFYnBpwlEn2pT1qUxJ8TJswxdXRcGCQSAA)

Note that you cannot assert your way to anything - basically it is only for refining types. Therefore it is not the same as "casting" a type.

You can also assert a property is non-null, when accessing it:

```ts
element.parentNode!.removeChild(element) // ! before the period
myFunction(document.getElementById(dialog.id!)! // ! after the property accessing
let userID!: string // definite assignment assertion... be careful!
```

Of course, try to actually handle the null case instead of asserting :)

## Simulating Nominal Types

TS' structural typing is handy, until it is inconvenient. However you can simulate nominal typing with [`type branding`](https://basarat.gitbook.io/typescript/main-1/nominaltyping):

```ts
type OrderID = string & { readonly brand: unique symbol };
type UserID = string & { readonly brand: unique symbol };
type ID = OrderID | UserID;
```

We can create these values with the Companion Object Pattern:

```ts
function OrderID(id: string) {
  return id as OrderID;
}
function UserID(id: string) {
  return id as UserID;
}
```

Now TypeScript will disallow you from using the wrong ID in the wrong place:

```ts
function queryForUser(id: UserID) {
  // ...
}
queryForUser(OrderID("foobar")); // Error, Argument of type 'OrderID' is not assignable to parameter of type 'UserID'
```

In future you can use the `unique` keyword to brand. [See this PR](https://github.com/microsoft/TypeScript/pull/33038).

## Intersection Types

Adding two types together can be handy, for example when your component is supposed to mirror the props of a native component like a `button`:

```tsx
export interface Props {
  label: string;
}
export const PrimaryButton = (
  props: Props & React.HTMLProps<HTMLButtonElement> // adding my Props together with the @types/react button provided props
) => <Button {...props} />;
```

You can also use Intersection Types to make reusable subsets of props for similar components:

```tsx
type BaseProps = {
   className?: string,
   style?: React.CSSProperties
   name: string // used in both
}
type DogProps = {
  tailsCount: number
}
type HumanProps = {
  handsCount: number
}
export const Human: React.FC<BaseProps & HumanProps> = // ...
export const Dog: React.FC<BaseProps & DogProps> = // ...
```

[View in the TypeScript Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgcilQ3wFgAoCmATzCTgCEUBnJABRzGbgF44BvCnGFoANi2YA5FCCQB+AFxxmMKMAB2AcwA0Q4Suqj5S5OhgA6AMIBlaxwh1YwJMz1x1MpEpVqtcAPT+cACurAAmcBpwAEYQMAAWFAC+VLT0ACIQmvZcvAJ6MCjAosyWEMHqMErqwSDRSFDJqXRwABK1KOo53HyC5MLxnWGl5ZXVtfWN5CnkSAAekLBwaBDqKm0d6ibEFgBilgA8TKzdcABkGyCd3QB8eQAUAJS8d-d6B2HAAG4BNxSPFAo80W8BWa3gmU02zM5n2RxY7E43AukNuD2ePFe70+P38f3IjyAA)

Make sure not to confuse Intersection Types (which are **and** operations) with Union Types (which are **or** operations).

## Union Types

This section is yet to be written (please contribute!). Meanwhile, see our [commentary on Union Types usecases](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/blob/master/README.md#union-types-and-type-guarding).

The ADVANCED cheatsheet also has information on Discriminated Union Types, which are helpful when TypeScript doesn't seem to be narrowing your union type as you expect.

## Overloading Function Types

Specifically when it comes to functions, you may need to overload instead of union type. The most common way function types are written uses the shorthand:

```ts
type FunctionType1 = (x: string, y: number) => number;
```

But this doesn't let you do any overloading. If you have the implementation, you can put them after each other with the function keyword:

```ts
function pickCard(x: { suit: string; card: number }[]): number;
function pickCard(x: number): { suit: string; card: number };
function pickCard(x): any {
  // implementation with combined signature
  // ...
}
```

However, if you don't have an implementation and are just writing a `.d.ts` definition file, this won't help you either. In this case you can forego any shorthand and write them the old-school way. The key thing to remember here is as far as TypeScript is concerned, `functions are just callable objects with no key`:

```ts
type pickCard = {
  (x: { suit: string; card: number }[]): number;
  (x: number): { suit: string; card: number };
  // no need for combined signature in this form
  // you can also type static properties of functions here eg `pickCard.wasCalled`
};
```

Note that when you implement the actual overloaded function, the implementation will need to declare the combined call signature that you'll be handling, it won't be inferred for you. You can see readily see examples of overloads in DOM APIs, e.g. `createElement`.

[Read more about Overloading in the Handbook.](https://www.typescriptlang.org/docs/handbook/functions.html#overloads)

## Using Inferred Types

Leaning on TypeScript's Type Inference is great... until you realize you need a type that was inferred, and have to go back and explicitly declare types/interfaces so you can export them for reuse.

Fortunately, with `typeof`, you won't have to do that. Just use it on any value:

```tsx
const [state, setState] = React.useState({
  foo: 1,
  bar: 2,
}); // state's type inferred to be {foo: number, bar: number}

const someMethod = (obj: typeof state) => {
  // grabbing the type of state even though it was inferred
  // some code using obj
  setState(obj); // this works
};
```

## Using Partial Types

Working with slicing state and props is common in React. Again, you don't really have to go and explicitly redefine your types if you use the `Partial` generic type:

```tsx
const [state, setState] = React.useState({
  foo: 1,
  bar: 2,
}); // state's type inferred to be {foo: number, bar: number}

// NOTE: stale state merging is not actually encouraged in React.useState
// we are just demonstrating how to use Partial here
const partialStateUpdate = (obj: Partial<typeof state>) =>
  setState({ ...state, ...obj });

// later on...
partialStateUpdate({ foo: 2 }); // this works
```

<details>
  <summary>
    Minor caveats on using <code>Partial</code>
  </summary>

Note that there are some TS users who don't agree with using `Partial` as it behaves today. See [subtle pitfalls of the above example here](https://twitter.com/ferdaber/status/1084798596027957248), and check out this long discussion on [why @types/react uses Pick instead of Partial](https://github.com/DefinitelyTyped/DefinitelyTyped/issues/18365).

</details>

## The Types I need weren't exported!

This can be annoying but here are ways to grab the types!

- Grabbing the Prop types of a component: Use `React.ComponentProps` and `typeof`, and optionally `Omit` any overlapping types

```tsx
import { Button } from "library"; // but doesn't export ButtonProps! oh no!
type ButtonProps = React.ComponentProps<typeof Button>; // no problem! grab your own!
type AlertButtonProps = Omit<ButtonProps, "onClick">; // modify
const AlertButton: React.FC<AlertButtonProps> = (props) => (
  <Button onClick={() => alert("hello")} {...props} />
);
```

You may also use [`ComponentPropsWithoutRef`](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/a05cc538a42243c632f054e42eab483ebf1560ab/types/react/index.d.ts#L774) (instead of ComponentProps) and [`ComponentPropsWithRef`](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/a05cc538a42243c632f054e42eab483ebf1560ab/types/react/index.d.ts#L770) (if your component specifically forwards refs)

- Grabbing the return type of a function: use `ReturnType`:

```tsx
// inside some library - return type { baz: number } is inferred but not exported
function foo(bar: string) {
  return { baz: 1 };
}

//  inside your app, if you need { baz: number }
type FooReturn = ReturnType<typeof foo>; // { baz: number }
```

In fact you can grab virtually anything public: [see this blogpost from Ivan Koshelev](http://ikoshelev.azurewebsites.net/search/id/11/Pragmatic-uses-of-TypeScript-type-system-My-type-of-type)

```ts
function foo() {
  return {
    a: 1,
    b: 2,
    subInstArr: [
      {
        c: 3,
        d: 4,
      },
    ],
  };
}

type InstType = ReturnType<typeof foo>;
type SubInstArr = InstType["subInstArr"];
type SubIsntType = SubInstArr[0];

let baz: SubIsntType = {
  c: 5,
  d: 6, // type checks ok!
};

//You could just write a one-liner,
//But please make sure it is forward-readable
//(you can understand it from reading once left-to-right with no jumps)
type SubIsntType2 = ReturnType<typeof foo>["subInstArr"][0];
let baz2: SubIsntType2 = {
  c: 5,
  d: 6, // type checks ok!
};
```

- TS also ships with a `Parameters` utility type for extracting the parameters of a function
- for anything more "custom", the `infer` keyword is the basic building block for this, but takes a bit of getting used to. Look at the source code for the above utility types, and [this example](https://twitter.com/mgechev/status/1211030455224422401?s=20) to get the idea. Basarat [also has a good video on `infer`](https://www.youtube.com/watch?v=ijK-1R-LFII&list=PLYvdvJlnTOjF6aJsWWAt7kZRJvzw-en8B&index=3&t=0s).

## The Types I need don't exist!

What's more annoying than modules with unexported types? Modules that are **untyped**!

> Before you proceed - make sure you have checked that types don't exist in [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped) or [TypeSearch](https://microsoft.github.io/TypeSearch/)

Fret not! There are more than a couple of ways in which you can solve this problem.

### Slapping `any` on everything

A **lazier** way would be to create a new type declaration file, say `typedec.d.ts`– if you don't already have one. Ensure that the path to file is resolvable by TypeScript by checking the `include` array in the `tsconfig.json` file at the root of your directory.

```json
// inside tsconfig.json
{
  // ...
  "include": [
    "src" // automatically resolves if the path to declaration is src/typedec.d.ts
  ]
  // ...
}
```

Within this file, add the `declare` syntax for your desired module, say `my-untyped-module`– to the declaration file:

```ts
// inside typedec.d.ts
declare module "my-untyped-module";
```

This one-liner alone is enough if you just need it to work without errors. A even hackier, write-once-and-forget way would be to use `"*"` instead which would then apply the `Any` type for all existing and future untyped modules.

This solution works well as a workaround if you have less than a couple untyped modules. Anything more, you now have a ticking type-bomb in your hands. The only way of circumventing this problem would be to define the missing types for those untyped modules as explained in the following sections.

### Autogenerate types

You can use TypeScript with `--allowJs` and `--declaration` to see TypeScript's "best guess" at the types of the library.

If this doesn't work well enough, use [`dts-gen`](https://github.com/Microsoft/dts-gen) to use the runtime shape of the object to accurately enumerate all available properties. This tends to be very accurate, BUT the tool does not yet support scraping JSDoc comments to populate additional types.

```bash
npm install -g dts-gen
dts-gen -m <your-module>
```

There are other automated JS to TS conversion tools and migration strategies - see [our MIGRATION cheatsheet](https://react-typescript-cheatsheet.netlify.app/docs/migration/from_js).

### Typing Exported Hooks

Typing Hooks is just like typing pure functions.

The following steps work under two assumptions:

- You have already created a type declaration file as stated earlier in the section.
- You have access to the source code - specifically the code that directly exports the functions you will be using. In most cases, it would be housed in an `index.js` file.
  Typically you need a minimum of **two** type declarations (one for **Input Prop** and the other for **Return Prop**) to define a hook completely. Suppose the hook you wish to type follows the following structure,

```js
// ...
const useUntypedHook = (prop) => {
  // some processing happens here
  return {
    /* ReturnProps */
  };
};
export default useUntypedHook;
```

then, your type declaration should most likely follow the following syntax.

```ts
declare module 'use-untyped-hook' {
  export interface InputProps { ... }   // type declaration for prop
  export interface ReturnProps { ... } // type declaration for return props
  export default function useUntypedHook(
    prop: InputProps
    // ...
  ): ReturnProps;
}
```

<details>
<summary>

For instance, the [useDarkMode hook](https://github.com/donavon/use-dark-mode) exports the functions that follows a similar structure.

</summary>

```js
// inside src/index.js
const useDarkMode = (
  initialValue = false, // -> input props / config props to be exported
  {
    // -> input props / config props to be exported
    element,
    classNameDark,
    classNameLight,
    onChange,
    storageKey = "darkMode",
    storageProvider,
    global,
  } = {}
) => {
  // ...
  return {
    // -> return props to be exported
    value: state,
    enable: useCallback(() => setState(true), [setState]),
    disable: useCallback(() => setState(false), [setState]),
    toggle: useCallback(() => setState((current) => !current), [setState]),
  };
};
export default useDarkMode;
```

As the comments suggest, exporting these config props and return props following the aforementioned structure will result in the following type export.

```ts
declare module "use-dark-mode" {
  /**
   * A config object allowing you to specify certain aspects of `useDarkMode`
   */
  export interface DarkModeConfig {
    classNameDark?: string; // A className to set "dark mode". Default = "dark-mode".
    classNameLight?: string; // A className to set "light mode". Default = "light-mode".
    element?: HTMLElement; // The element to apply the className. Default = `document.body`
    onChange?: (val?: boolean) => void; // Overide the default className handler with a custom callback.
    storageKey?: string; // Specify the `localStorage` key. Default = "darkMode". Set to `null` to disable persistent storage.
    storageProvider?: WindowLocalStorage; // A storage provider. Default = `localStorage`.
    global?: Window; // The global object. Default = `window`.
  }
  /**
   * An object returned from a call to `useDarkMode`.
   */
  export interface DarkMode {
    readonly value: boolean;
    enable: () => void;
    disable: () => void;
    toggle: () => void;
  }
  /**
   * A custom React Hook to help you implement a "dark mode" component for your application.
   */
  export default function useDarkMode(
    initialState?: boolean,
    config?: DarkModeConfig
  ): DarkMode;
}
```

</details>

### Typing Exported Components

In case of typing untyped class components, there's almost no difference in approach except for the fact that after declaring the types, you export the extend the type using `class UntypedClassComponent extends React.Component<UntypedClassComponentProps, any> {}` where `UntypedClassComponentProps` holds the type declaration.

For instance, [sw-yx's Gist on React Router 6 types](https://gist.github.com/sw-yx/37a6a3d248c2d4031801f0d568904df8) implemented a similar method for typing the then untyped RR6.

```ts
declare module "react-router-dom" {
  import * as React from 'react';
  // ...
  type NavigateProps<T> = {
    to: string | number,
    replace?: boolean,
    state?: T
  }
  //...
  export class Navigate<T = any> extends React.Component<NavigateProps<T>>{}
  // ...
```

For more information on creating type definitions for class components, you can refer to this [post](https://templecoding.com/blog/2016/03/31/creating-typescript-typings-for-existing-react-components) for reference.

<!--END-SECTION:types-->

<!--START-SECTION:operators-->

# Troubleshooting Handbook: Operators

- `typeof` and `instanceof`: type query used for refinement
- `keyof`: get keys of an object
- `O[K]`: property lookup
- `[K in O]`: mapped types
- `+` or `-` or `readonly` or `?`: addition and subtraction and readonly and optional modifiers
- `x ? Y : Z`: Conditional types for generic types, type aliases, function parameter types
- `!`: Nonnull assertion for nullable types
- `=`: Generic type parameter default for generic types
- `as`: type assertion
- `is`: type guard for function return types

Conditional Types are a difficult topic to get around so here are some extra resources:

- fully walked through explanation https://artsy.github.io/blog/2018/11/21/conditional-types-in-typescript/
- Bailing out and other advanced topics https://github.com/sw-yx/ts-spec/blob/master/conditional-types.md
- Basarat's video https://www.youtube.com/watch?v=SbVgPQDealg&list=PLYvdvJlnTOjF6aJsWWAt7kZRJvzw-en8B&index=2&t=0s

<!--END-SECTION:operators-->

<!--START-SECTION:utilities-->

# Troubleshooting Handbook: Utilities

These are all built in, [see source in es5.d.ts](https://github.com/microsoft/TypeScript/blob/2c458c0d1ccb96442bca9ce43aa987fb0becf8a9/src/lib/es5.d.ts#L1401-L1474):

- `ConstructorParameters`: a tuple of class constructor's parameter types
- `Exclude`: exclude a type from another type
- `Extract`: select a subtype that is assignable to another type
- `InstanceType`: the instance type you get from a `new`ing a class constructor
- `NonNullable`: exclude `null` and `undefined` from a type
- `Parameters`: a tuple of a function's parameter types
- `Partial`: Make all properties in an object optional
- `Readonly`: Make all properties in an object readonly
- `ReadonlyArray`: Make an immutable array of the given type
- `Pick`: A subtype of an object type with a subset of its keys
- `Record`: A map from a key type to a value type
- `Required`: Make all properties in an object required
- `ReturnType`: A function's return type

<!--END-SECTION:utilities-->

<!--START-SECTION:ts-config-->

# Troubleshooting Handbook: tsconfig.json

You can find [all the Compiler options in the TypeScript docs](https://www.typescriptlang.org/docs/handbook/compiler-options.html). [The new TS docs also has per-flag annotations of what each does](https://www.typescriptlang.org/tsconfig#allowSyntheticDefaultImports). This is the setup I roll with for APPS (not libraries - for libraries you may wish to see the settings we use in `tsdx`):

```json
{
  "compilerOptions": {
    "incremental": true,
    "outDir": "build/lib",
    "target": "es5",
    "module": "esnext",
    "lib": ["dom", "esnext"],
    "sourceMap": true,
    "importHelpers": true,
    "declaration": true,
    "rootDir": "src",
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,
    "allowJs": false,
    "jsx": "react",
    "moduleResolution": "node",
    "baseUrl": "src",
    "forceConsistentCasingInFileNames": true,
    "esModuleInterop": true,
    "suppressImplicitAnyIndexErrors": true,
    "allowSyntheticDefaultImports": true,
    "experimentalDecorators": true
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "build", "scripts"]
}
```

You can find more [recommended TS config here](https://github.com/tsconfig/bases).

Please open an issue and discuss if there are better recommended choices for React.

Selected flags and why we like them:

- `esModuleInterop`: disables namespace imports (`import * as foo from "foo"`) and enables CJS/AMD/UMD style imports (`import fs from "fs"`)
- `strict`: `strictPropertyInitialization` forces you to initialize class properties or explicitly declare that they can be undefined. You can opt out of this with a definite assignment assertion.
- `"typeRoots": ["./typings", "./node_modules/@types"]`: By default, TypeScript looks in `node_modules/@types` and parent folders for third party type declarations. You may wish to override this default resolution so you can put all your global type declarations in a special `typings` folder.

Compilation speed grows linearly with size of codebase. For large projects, you will want to use [Project References](https://www.typescriptlang.org/docs/handbook/project-references.html). See our [ADVANCED](https://react-typescript-cheatsheet.netlify.app/docs/advanced/intro/) cheatsheet for commentary.

<!--END-SECTION:ts-config-->

<!--START-SECTION:official-typings-bugs-->

# Troubleshooting Handbook: Fixing bugs in official typings

If you run into bugs with your library's official typings, you can copy them locally and tell TypeScript to use your local version using the "paths" field. In your `tsconfig.json`:

```json
{
  "compilerOptions": {
    "paths": {
      "mobx-react": ["../typings/modules/mobx-react"]
    }
  }
}
```

[Thanks to @adamrackis for the tip.](https://twitter.com/AdamRackis/status/1024827730452520963)

If you just need to add an interface, or add missing members to an existing interface, you don't need to copy the whole typing package. Instead, you can use [declaration merging](https://www.typescriptlang.org/docs/handbook/declaration-merging.html):

```tsx
// my-typings.ts
declare module "plotly.js" {
  interface PlotlyHTMLElement {
    removeAllListeners(): void;
  }
}

// MyComponent.tsx
import { PlotlyHTMLElement } from "plotly.js";

const f = (e: PlotlyHTMLElement) => {
  e.removeAllListeners();
};
```

You dont always have to implement the module, you can simply import the module as `any` for a quick start:

```tsx
// my-typings.ts
declare module "plotly.js"; // each of its imports are `any`
```

Because you don't have to explicitly import this, this is known as an [ambient module declaration](https://www.typescriptlang.org/docs/handbook/namespaces-and-modules.html#pitfalls-of-namespaces-and-modules). You can do AMD's in a script-mode `.ts` file (no imports or exports), or a `.d.ts` file anywhere in your project.

You can also do ambient variable and ambient type declarations:

```ts
// ambient utiltity type
type ToArray<T> = T extends unknown[] ? T : T[];
// ambient variable
declare let process: {
  env: {
    NODE_ENV: "development" | "production";
  };
};
process = {
  env: {
    NODE_ENV: "production",
  },
};
```

You can see examples of these included in the built in type declarations in the `lib` field of `tsconfig.json`

<!--END-SECTION:official-typings-bugs-->

<!--START-SECTION:non-ts-files-->

# Time to Really Learn TypeScript

Believe it or not, we have only barely introduced TypeScript here in this cheatsheet. There is a whole world of generic type logic that you will eventually get into, however it becomes far less dealing with React than just getting good at TypeScript so it is out of scope here. But at least you can get productive in React now :)

It is worth mentioning some resources to help you get started:

- Step through the 40+ examples under [the playground's](http://www.typescriptlang.org/play/index.html) Examples section, written by @Orta
- Anders Hejlsberg's overview of TS: https://www.youtube.com/watch?v=ET4kT88JRXs
- Marius Schultz: https://blog.mariusschulz.com/series/typescript-evolution with an [Egghead.io course](https://egghead.io/courses/advanced-static-types-in-typescript)
- Basarat's Deep Dive: https://basarat.gitbook.io/typescript/
- Rares Matei: [Egghead.io course](https://egghead.io/courses/practical-advanced-typescript)'s advanced TypeScript course on Egghead.io is great for newer typescript features and practical type logic applications (e.g. recursively making all properties of a type `readonly`)
- Shu Uesugi: [TypeScript for Beginner Programmers](https://ts.chibicode.com/)

<!--END-SECTION:non-ts-files-->

<!--START-SECTION:resources-->

# Other React + TypeScript resources

- me! <https://twitter.com/swyx>
- https://www.freecodecamp.org/news/how-to-build-a-todo-app-with-react-typescript-nodejs-and-mongodb/
- <https://github.com/piotrwitek/react-redux-typescript-guide> - **HIGHLY HIGHLY RECOMMENDED**, i wrote this repo before knowing about this one, this has a lot of stuff I don't cover, including **REDUX** and **JEST**.
- [Ultimate React Component Patterns with TypeScript 2.8](https://levelup.gitconnected.com/ultimate-react-component-patterns-with-typescript-2-8-82990c516935)
- [Basarat's TypeScript gitbook has a React section](https://basarat.gitbook.io/typescript/tsx/react) with an [Egghead.io course](https://egghead.io/courses/use-typescript-to-develop-react-applications) as well.
- [Palmer Group's TypeScript + React Guidelines](https://github.com/palmerhq/typescript) as well as Jared's other work like [disco.chat](https://github.com/jaredpalmer/disco.chat)
- [Sindre Sorhus' TypeScript Style Guide](https://github.com/sindresorhus/typescript-definition-style-guide)
- [TypeScript React Starter Template by Microsoft](https://github.com/Microsoft/TypeScript-React-Starter) A starter template for TypeScript and React with a detailed README describing how to use the two together. Note: this doesnt seem to be frequently updated anymore.
- [Brian Holt's Intermediate React course on Frontend Masters (paid)](https://frontendmasters.com/courses/intermediate-react/converting-the-app-to-typescript/) - Converting App To TypeScript Section
- [Mike North's Production TypeScript course on Frontend Masters (paid)](https://frontendmasters.com/courses/production-typescript/)
- [TSX Guide](https://jenil.github.io/chota/) by [gojutin](https://github.com/gojutin/www.tsx.guide)
- TypeScript conversion:
  - [Lyft's React-To-TypeScript conversion CLI](https://github.com/lyft/react-javascript-to-typescript-transform)
  - [Gustav Wengel's blogpost - converting a React codebase to TypeScript](http://www.gustavwengel.dk/converting-typescript-to-javascript-part-1)
  - [Microsoft React TypeScript conversion guide](https://github.com/Microsoft/TypeScript-React-Conversion-Guide#typescript-react-conversion-guide)
- [You?](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:resources-->

<!--START-SECTION:editor-integration-->

# Editor Tooling and Integration

- VSCode
  - swyx's VSCode Extension: https://github.com/sw-yx/swyx-react-typescript-snippets
  - amVim: https://marketplace.visualstudio.com/items?itemName=auiworks.amvim
- VIM
  - https://github.com/Quramy/tsuquyomi
  - nvim-typescript?
  - https://github.com/leafgarland/typescript-vim
  - peitalin/vim-jsx-typescript
  - NeoVim: https://github.com/neoclide/coc.nvim
  - other discussion: https://mobile.twitter.com/ryanflorence/status/1085715595994095620

You are free to use this repo's TSX logo if you wish:

[![https://user-images.githubusercontent.com/6764957/53868378-2b51fc80-3fb3-11e9-9cee-0277efe8a927.png](https://user-images.githubusercontent.com/6764957/53868378-2b51fc80-3fb3-11e9-9cee-0277efe8a927.png)](https://user-images.githubusercontent.com/6764957/53868378-2b51fc80-3fb3-11e9-9cee-0277efe8a927.png)

You may also wish to use alternative logos - [jsx-tsx-logos](https://github.com/Protectator/jsx-tsx-logos)

![https://github.com/Protectator/jsx-tsx-logos/raw/master/example.png](https://github.com/Protectator/jsx-tsx-logos/raw/master/example.png)

<!--END-SECTION:editor-integration-->

<!--START-SECTION:linting-->

# Linting

> ⚠️Note that [TSLint is now in maintenance and you should try to use ESLint instead](https://medium.com/palantir/tslint-in-2019-1a144c2317a9). If you are interested in TSLint tips, please check this PR from [@azdanov](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/pull/14). The rest of this section just focuses on ESLint. [You can convert TSlint to ESlint with this tool](https://github.com/typescript-eslint/tslint-to-eslint-config).

> ⚠️This is an evolving topic. `typescript-eslint-parser` is no longer maintained and [work has recently begun on `typescript-eslint` in the ESLint community](https://eslint.org/blog/2019/01/future-typescript-eslint) to bring ESLint up to full parity and interop with TSLint.

Follow the TypeScript + ESLint docs at https://github.com/typescript-eslint/typescript-eslint:

```
yarn add -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint
```

add a `lint` script to your `package.json`:

```json
  "scripts": {
    "lint": "eslint 'src/**/*.ts'"
  },
```

and a suitable `.eslintrc.js` (using `.js` over `.json` here so we can add comments):

```js
module.exports = {
  env: {
    es6: true,
    node: true,
    jest: true,
  },
  extends: "eslint:recommended",
  parser: "@typescript-eslint/parser",
  plugins: ["@typescript-eslint"],
  parserOptions: {
    ecmaVersion: 2017,
    sourceType: "module",
  },
  rules: {
    indent: ["error", 2],
    "linebreak-style": ["error", "unix"],
    quotes: ["error", "single"],
    "no-console": "warn",
    "no-unused-vars": "off",
    "@typescript-eslint/no-unused-vars": [
      "error",
      { vars: "all", args: "after-used", ignoreRestSiblings: false },
    ],
    "@typescript-eslint/explicit-function-return-type": "warn", // Consider using explicit annotations for object literals and function return types even when they can be inferred.
    "no-empty": "warn",
  },
};
```

Most of this is taken from [the `tsdx` PR](https://github.com/palmerhq/tsdx/pull/70/files) which is for **libraries**.

More `.eslintrc.json` options to consider with more options you may want for **apps**:

```json
{
  "extends": [
    "airbnb",
    "prettier",
    "prettier/react",
    "plugin:prettier/recommended",
    "plugin:jest/recommended",
    "plugin:unicorn/recommended"
  ],
  "plugins": ["prettier", "jest", "unicorn"],
  "parserOptions": {
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "jest": true
  },
  "settings": {
    "import/resolver": {
      "node": {
        "extensions": [".js", ".jsx", ".ts", ".tsx"]
      }
    }
  },
  "overrides": [
    {
      "files": ["**/*.ts", "**/*.tsx"],
      "parser": "typescript-eslint-parser",
      "rules": {
        "no-undef": "off"
      }
    }
  ]
}
```

You can read a [fuller TypeScript + ESLint setup guide here](https://blog.matterhorn.dev/posts/learn-typescript-linting-part-1/) from Matterhorn, in particular check https://github.com/MatterhornDev/learn-typescript-linting.

Another great resource is ["Using ESLint and Prettier in a TypeScript Project"](https://dev.to/robertcoopercode/using-eslint-and-prettier-in-a-typescript-project-53jb) by @robertcoopercode.

Wes Bos is also working on [TypeScript support for his eslint+prettier config.](https://github.com/wesbos/eslint-config-wesbos/issues/68)

If you're looking for information on Prettier, check out the [Prettier](https://github.com/typescript-cheatsheets/react/blob/main/docs/advanced/misc-concerns.md#prettier) guide.

<!--END-SECTION:linting-->

<!--START-SECTION:other-resources-->

# Other React + TypeScript resources

- me! <https://twitter.com/swyx>
- <https://github.com/piotrwitek/react-redux-typescript-guide> - **HIGHLY HIGHLY RECOMMENDED**, i wrote this repo before knowing about this one, this has a lot of stuff I don't cover, including **REDUX** and **JEST**.
- [Ultimate React Component Patterns with TypeScript 2.8](https://levelup.gitconnected.com/ultimate-react-component-patterns-with-typescript-2-8-82990c516935)
- [Basarat's TypeScript gitbook has a React section](https://basarat.gitbook.io/typescript/tsx/react) with an [Egghead.io course](https://egghead.io/courses/use-typescript-to-develop-react-applications) as well.
- [Palmer Group's TypeScript + React Guidelines](https://github.com/palmerhq/typescript) as well as Jared's other work like [disco.chat](https://github.com/jaredpalmer/disco.chat)
- [Stefan Baumgartner's TypeScript + React Guide](https://fettblog.eu/typescript-react), which serves as a side-by-side guide to the official docs with extra articles on styling, custom hooks and patterns
- [Sindre Sorhus' TypeScript Style Guide](https://github.com/sindresorhus/typescript-definition-style-guide)
- [TypeScript React Starter Template by Microsoft](https://github.com/Microsoft/TypeScript-React-Starter) A starter template for TypeScript and React with a detailed README describing how to use the two together. Note: this doesnt seem to be frequently updated anymore.
- [Brian Holt's Intermediate React course on Frontend Masters (paid)](https://frontendmasters.com/courses/intermediate-react/converting-the-app-to-typescript/) - Converting App To TypeScript Section
- TypeScript conversion:
  - [Lyft's React-To-TypeScript conversion CLI](https://github.com/lyft/react-javascript-to-typescript-transform)
  - [Gustav Wengel's blogpost - converting a React codebase to TypeScript](http://www.gustavwengel.dk/converting-typescript-to-javascript-part-1)
  - [Microsoft React TypeScript conversion guide](https://github.com/Microsoft/TypeScript-React-Conversion-Guide#typescript-react-conversion-guide)
- [DefinitelyTyped React source code](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/react)
- [You?](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

<!--END-SECTION:other-resources-->

<!--START-SECTION:talks-->

# Recommended React + TypeScript talks

- [Ultimate React Component Patterns with TypeScript](https://www.youtube.com/watch?v=_PBQ3if6Fmg), by Martin Hochel, GeeCon Prague 2018
- Please help contribute this new section!

<!--END-SECTION:talks-->

<!--START-SECTION:learn-ts-->

# Time to Really Learn TypeScript

Believe it or not, we have only barely introduced TypeScript here in this cheatsheet. There is a whole world of generic type logic that you will eventually get into, however it becomes far less dealing with React than just getting good at TypeScript so it is out of scope here. But at least you can get productive in React now :)

It is worth mentioning some resources to help you get started:

- Step through the 40+ examples under [the playground's](http://www.typescriptlang.org/play/index.html) Examples section, written by @Orta
- Anders Hejlsberg's overview of TS: https://www.youtube.com/watch?v=ET4kT88JRXs
- Marius Schultz: https://blog.mariusschulz.com/series/typescript-evolution with an [Egghead.io course](https://egghead.io/courses/advanced-static-types-in-typescript)
- Basarat's Deep Dive: https://basarat.gitbook.io/typescript/
- Rares Matei: [Egghead.io course](https://egghead.io/courses/practical-advanced-typescript)'s advanced TypeScript course on Egghead.io is great for newer typescript features and practical type logic applications (e.g. recursively making all properties of a type `readonly`)
- Shu Uesugi: [TypeScript for Beginner Programmers](https://ts.chibicode.com/)

<!--END-SECTION:learn-ts-->

<!--START-SECTION:examples-->

# Example App

- [Create React App TypeScript Todo Example 2020](https://github.com/laststance/create-react-app-typescript-todo-example-2020)
- [Ben Awad's 14 hour Fullstack React/GraphQL/TypeScript Tutorial](https://www.youtube.com/watch?v=I6ypD7qv3Z8)
- [Cypress Realworld App](https://github.com/cypress-io/cypress-realworld-app)

<!--END-SECTION:examples-->

# My question isn't answered here!

- [File an issue](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new).

## Contributors

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. See [CONTRIBUTORS.md](/CONTRIBUTORS.md) for the full list. Contributions of any kind welcome!
