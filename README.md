This repository contains Angular project which helps to reproduce the issue [#213](https://github.com/ngneat/spectator/issues/213) of `@ngneat/spectator` library

Steps to reproduce:
1. run `npm install` to download all referenced packages
2. run `npm run build` to build the project

Actual behavior: build fails with the following error:
```diff
- ERROR in node_modules/@ngneat/spectator/jest/lib/matchers-types.d.ts(2,13): error TS2428: All declarations of 'Matchers' must have identical type parameters.
- node_modules/@ngneat/spectator/lib/mock.d.ts(1,23): error TS2688: Cannot find type definition file for 'jasmine'.
- node_modules/@types/jest/index.d.ts(667,15): error TS2428: All declarations of 'Matchers' must have identical type parameters.
```

But it builds fine if `@ngneat/spectator` is not used. For doing that:
1. open `src/app/app.component.spec.ts`
2. comment out line #3 `import { SpectatorFactory } from  '@ngneat/spectator/jest';`
3. run build once again
