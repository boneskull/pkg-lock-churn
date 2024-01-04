# example of package-lock.json churn

This reproduces the issue in https://github.com/npm/cli/issues/6301

## Steps to reproduce

1. Use Node.js v20.10.0
2. Use npm v10.2.3
3. Clone this repo
4. Checkout the `conflict` branch
5. Rebase the `conflict` branch onto `main`.
6. Resolve the conflict in `packages/something/package.json` by combining the changes.
7. Run `npm install` to update `package-lock.json`.
8. Run `git diff` to see the churn in `package-lock.json`.

## Red Herrings Abound!

- I don't know if the workspace is necessary.
- I don't know if conflict resolution is necessary.

## Not a Red Herring

I can only seem to make this happen with `devDependencies`.
