## Frequently used npm commands

| Command | Description
| --- | ---
| `npm init` | Create a `package.json` file. Use `npm init -y` to generate a file without any questions
| `npm install` <br>`npm install <package-name> ...` <br>`npm i` <br>`npm i <package-name> ...` | Install all dependencies or install any provided package(s) <br><br>Flags: <br>`-g` - install a package to the global scope (it will be available in any of your projects) <br>`-D` - install a package to `devDependencies` <br>`-d` or `-P` - install a package to `dependencies` <br>`-O` - install a package to `optionalDependencies`
| `npm ci` | Install dependencies in safe mode
| `npm uninstall <package-name> ...` <br>`npm r <package-name> ...` | Delete the installed package(s) <br><br>`-g` - flag to delete the package(s) from the global scope
| `npm update` | Update packages to the last version
| `npm start` | Run a command `start` from `scripts`
| `npm stop` | Run a command `stop` from `scripts`
| `npm test` | Run a command `test` from `scripts`
| `npm run` | Display a list of all commands from `scripts`
| `npm run <command>` | Run a specific command from `scripts`
| `npx <package> <command>` | Run a command from a local or remote npm package
| `npm repo` | Open package repository page in the browser
| `npm docs` | Open documentation for a package in a web browser
| `npm publish` | Publish a package to `npm`. Use `npx npm-packlist` to see what will be included in your package. Use `npm publish --access public` to publish a scoped package (@user/package-name).
| `npm version <new-version>` | Set a new version of the package
| `npm ls` | List all installed packages. Use `-g` to see global packages

### Difference between `npm i` and `npm ci`
- `npm i` - install all dependencies, can modify `package.json` or `package-lock.json`, may not install the exact version you specified;
- `npm ci` - install all dependencies with the exact version, removes `node_modules` to ensure a clean state, never writes to `package.json` or `package-lock.json`.

### Links

- [List of all commands](https://docs.npmjs.com/cli/v7/commands)
- [npm ci vs. npm install - Which Should You Use in Your Node.js Projects?](https://betterprogramming.pub/npm-ci-vs-npm-install-which-should-you-use-in-your-node-js-projects-51e07cb71e26)
- [What is the difference between “npm install” and “npm ci”?](https://stackoverflow.com/questions/52499617/what-is-the-difference-between-npm-install-and-npm-ci)
