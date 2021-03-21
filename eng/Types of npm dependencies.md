## Types of npm dependencies

- **dependencies** - These are your normal dependencies, that you need when running your code (react, lodash, ...).
- **devDependencies** - These are your development dependencies, bundlers, transpilers and so on (webpack, rollup, babel, ...).
- **peerDependencies** - These dependencies are similar to **dependencies**, but they won't be installed automatically. You need to install them manually. This is useful for packages that need a big dependency like `react`. If this big dependency isn't installed, the warning is thrown.
- **optionalDependencies** - If these dependencies are not installed, nothing will happen. It is assumed that you have a fallback for this case. For example, if `jquery` is not installed, you will use pure js.
- **bundledDependencies** - These dependencies are used in case when they are not in npm registry or you want to use own modules for your projects but don't want to create and support npm package.

### Links
- [Types of dependencies](https://classic.yarnpkg.com/en/docs/dependency-types)
