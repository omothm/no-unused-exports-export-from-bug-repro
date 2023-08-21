# no-unused-exports export-from bug repro

A reproduction of a bug when `export * from` syntax is used with `canonical/no-unused-exports` ESLint rule.

## Description

When a file uses the syntax

```ts
export * from "./file.ts";
```

where `file.ts` contains more than one export on separate lines, the rule throws a `RangeError`.

## Reproduction

Run the following to see the error:

    $ npm run lint

This error is not related to the underlying tool (`ts-unused-exports`). Running the following does not throw errors:

    $ npm run ts-unused-exports
