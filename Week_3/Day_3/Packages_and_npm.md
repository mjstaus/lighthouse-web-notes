## Packages and npm
npm is Node's package manager - allows us to install and use open-source JS packages!

### What are Packages?
Package = self-contined library that we can install and use in our projects

Library = collection of pre-written code. They can be private, or they can be public/commercial products! Examples are jQuery and Bootstrap

### Installing Packages

Run in terminal: ```npm install packageName```

### Package.json

Node projects have a file called ```package.json``` that looks like this:

```
{
  "name": "project-name",
  "version": "1.0.0",
  "description": "Short project summary",
  "main": "index.js",
  "scripts": {
    "myscript": "ENV=development node index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "MIT",
  "dependencies": {
    "express": "^4.13.4"
  }
}
```
Here's the documentation to reference: https://docs.npmjs.com/files/package.json


- Scripts portion allows us to run commands using an alias
eg. ```npm run myscript```

- Dependencies are the packages that need to be installed for the project to run properly

### The ```package-lock.json``` File
- Lists all the details about the project's dependencies
- Should be checked into Git, along with ```package.json``` (whereas node_modules dir is ignored)
- Always avoid editing this file! We modify it indirectly through commands like npm install
- Read documentation here: https://docs.npmjs.com/cli/v7/configuring-npm/package-lock-json

#### ```require``` for Installed Packages
- Require allows us to import any installed packages (eg. chalk) into our JS files within our working directory

eg.

```javascript
const chalk = require("chalk");

const message = `Hello ${chalk.yellow("World")}`;
console.log(message);
```


### Stretch Readings:
1. Semantic Versioning = common syntax used in software: https://semver.org/
2. Node-semver is used to parse Node package versions: https://github.com/npm/node-semver



