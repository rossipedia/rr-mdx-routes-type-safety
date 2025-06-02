# MDX Routes don't typecheck

To reproduce:

```bash
$ pnpm install
$ pnpm typecheck
```

Output:

```bash
$ pnpm typecheck

> rr-mdx-routes-type-safety@ typecheck /Users/bryanross/src/rr/rr-mdx-routes-type-safety
> react-router typegen && tsc --build --noEmit

.react-router/types/app/routes/+types/_.about.ts:5:29 - error TS2307: Cannot find module '../_.about.js' or its corresponding type declarations.

5 type Module = typeof import("../_.about.js")
                              ~~~~~~~~~~~~~~~

.react-router/types/app/routes/+types/_.about.ts:20:25 - error TS2307: Cannot find module '../_.about.js' or its corresponding type declarations.

20   module: typeof import("../_.about.js");
                           ~~~~~~~~~~~~~~~


Found 2 errors.

 ELIFECYCLE  Command failed with exit code 1.
```