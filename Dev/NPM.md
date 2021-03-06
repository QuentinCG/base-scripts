# NPM

NPM is a packet manager for js projects.

## Install (NPM and NodeJs)

Download and install from https://www.npmjs.com/get-npm (add NPM to path if using windows)

## Initialize a project

Execute `npm init` in root of your project (It will create a `package.json`)

You could also create a `package.json` file following this standard:
```
{
  "name": "PROJECT_NAME_HERE",
  "version": "1.0.0",
  "description": "DESCRIPTION_HERE",
  "repository": {
    "type": "git",
    "url": "https://github.com/QuentinCG/REPO_HERE.git"
  },
  "bugs": {
    "url": "https://github.com/QuentinCG/REPO_HERE/issues"
  },
  "homepage": "https://github.com/QuentinCG/REPO_HERE",
  "author": "Quentin Comte-Gaz",
  "license": "MIT",
  "main": "index.js",
  "dependencies": {
  },
  "scripts": {
    "start": "npm run dev",
    "dev": "webpack --mode development --watch",
    "prod": "webpack --mode production --watch",
    "build": "webpack --mode production",
    "ANYTHING_HERE": "CMD_TO_EXECUTE_HERE_WHEN 'npm run ANYTHING_HERE' IS_USED_FROM_CMD"
  },
  "devDependencies": {
    "nodemon": "*",
    "webpack": "^4.30.0",
    "webpack-cli": "^3.3.1",
    "webpack-dev-server": "^3.7.2"
  },
}
```

## Add/Update dependencies to a project

`npm install` (with some potential parameters) will update `package.json` and add the lib in `node_modules` folder)

- Use `npm install --save DEPENDENCY_HERE` (or `DEPENDENCY_HERE`) to save the dependency in the project
- Use `npm install --save-dev DEPENDENCY_HERE` to save the dev dependency in the project
- Use `npm install --global DEPENDENCY_HERE` to install the package in your computer (for all projects but not stored in the `package.json` project file)
- Use `npm install` to update the `node_modules` folder (will install dependencies and devDependencies)
- Use `npm install --production` to update the `node_modules` folder (will install dependencies without devDependencies)


# Useful NPM packages

## Npm run all (run multiple commands in one command)

- Install: `npm install --save-dev npm-run-all`
- Usage: `npm-run-all CMD1 CMD2 ...`

## Nodemon (restarts node app when file change detected)

- Install: `npm install --save-dev nodemon`
- <a target="_blank" href="https://github.com/remy/nodemon#usage">Usage</a>: `nodemon [node app here]`

## Webpack (Bundling and Packaging ressources and assets)

- Install: `npm install --save-dev webpack webpack-cli webpack-dev-server` (+ <a target="_blank" href="https://webpack.js.org/configuration/">configure a `webpack.config.js` file manually or with `npx webpack-cli init` command</a>)
- <a target="_blank" href="https://www.npmjs.com/package/webpack">Tools linked to webpack</a>; css-loader, sass, typescript, ...
- <a target="_blank" href="https://webpack.js.org/guides/getting-started/">Getting started</a>

## Axios (Do request to HTTP client/API)

- Install: `npm install axios`
- <a target="_blank" href="https://github.com/axios/axios#example">Usage</a>:
```
const httpRequest = require('axios');

// Make a request for a user with a given ID
httpRequest.get('/user?ID=12345')
  .then(function (response) {
    // handle success
    console.log(response);
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .finally(function () {
    // always executed
  });
```

## Mongoose (Communicate with a MongoDB database)

- Install: `npm install mongoose`
- <a target="_blank" href="https://mongoosejs.com/docs/index.html">Usage</a>:
```
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost:27017/test', {useNewUrlParser: true});

const Cat = mongoose.model('Cat', { name: String });

const kitty = new Cat({ name: 'Zildjian' });
kitty.save().then(() => console.log('meow'));
```
- Additional information: Create a free 512MB MongoDB cluster from https://www.mongodb.com/ (Try Free -> Choose cluster -> Create a DB user with read/write access -> Whitelist all IP if in dev mode, else only your server IP -> Get link to connect to your app with pass of the DB user)

## Bootstrap (CSS framework)

- Install: `npm install bootstrap` (and <a target="_blank" href="https://getbootstrap.com/docs/4.3/getting-started/webpack/">integrate it with webpack</a> if you use webpack)
- <a target="_blank" href="https://getbootstrap.com/docs/4.3/components/">Usage</a>
- Important:
  - If using react, also install `react-bootstrap` package (<a target="_blank" href="https://react-bootstrap.github.io/getting-started/introduction/">more information here</a>)
  - If using vuejs, also install `bootstrap-vue` package (<a target="_blank" href="https://bootstrap-vue.js.org/docs">more information here</a>)
  - If using angular: TODO

## Bulma (CSS framework)

- Install: `npm install bulma`
- <a target="_blank" href="https://bulma.io/documentation/overview/start/">Usage</a>

## Sass (CSS compiler)

- Install: `npm install node-sass sass-loader style-loader node-sass-chokidar --save-dev`
- <a target="_blank" href="https://sass-lang.com/guide">Usage</a>:
```
@import '../node_modules/bulma/bulma.sass'

#app
  color: #ffffff
  margin-top: 60px
```

## Vue.js (Js framework)

- Install with help: `npm install --global vue-cli` (without help to integrate vue.js in existing project: `npm install vue`)
- Usage:
```
# Create a vue.js project with webpack
vue init webpack PROJECT_NAME
cd PROJECT_NAME
# Build the project
npm install
# Launch the project
npm run dev
```

## React (Js framework)

- Install with help: `npm install --global create-react-app` (without help to integrate in existing project: `npm install react react-router-dom`)
- <a target="_blank" href="https://create-react-app.dev/docs/getting-started">Usage</a>:
```
create-react-app PROJECT_NAME
cd PROJECT_NAME
# Build and launch the project
npm start
```

## Angular (Js/Typescript framework)

- Install with help: `npm install --global @angular/cli` (without help to integrate in existing project: `npm install angular`)
- <a target="_blank" href="https://angular.io/start">Usage</a>:
```
# Create an angular project with routing and sass
ng new PROJECT_NAME --routing --style=sass
cd PROJECT_NAME
# Build and launch the project
ng serve
# Generate a new component
ng generate component COMPONENT_NAME
```
