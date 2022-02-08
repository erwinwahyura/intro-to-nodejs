# intro-to-nodejs

## What is Node.js
Node.js is a runtime for built on top of Chrome's V8. It allows you to develop apps in JavaScript outside of the browser. It's single threaded non blocking and asynchronous. This is acheived by the use of an event loop at the core of Node.js. If you know JS then you already know how to develop with Node.js.

Because Node.js can run outside of the browser, it can be used for pretty much anything!

- API's and servers
- Databases (yes some DB's are built in Node)
- CLI's
- Build Tools
- Automations
- Basic Scripting
- GPU shopping bots 👀, etc.

### Installing Node.js
If you're running windows and not using WSL, I recommend you use the [official installer](https://nodejs.org/en/) from the Node.js site. Choose the latest LTS version.


If you're not on windows or you are using WSL, I recommend using installing Node.js with nvm (node version manager). NVM allows you to install many versions of Node.js at once and switch when you need. Also, NVM installs Node.js in a folder that will not have permission errors that you would otherwise run into with the official installer.

Once you have nvm installed, you need to install a Node version. You can download the latest LTS version with this command.

`nvm install --lts`

### Executing Node.js

#### Node REPL
Before we get into creating programs and apps with Node.js, let's get a feet wet with the Node.js REPL. Just type `node` in your terminal. This will create a Node.js environment where we can write and execute JavaScript. You'll see that all that JS knowledge you have learned carries over to Node.js! 💯. Although, some things, specifically browser based API's probably won't work. Go ahead, try an `alert('hello world')` and see what happens. You'll get an error. Although the Node.js runtime uses JS as it's languge, none of the Browser based globals that you are familiar with actually exist in Node.js or they are pollyfilled to prevent runtime errors.

#### File Execution

The Node REPL it nice, but you can't build an application with that. We need to be able write our code to a file and tell Node.js to execute that.

> Create a file called:index.js

In that file, write some JS. Try out `console.log('hello there')`. To execute this .js file in the Node.js runtime, we can use the `node` command with the file name as an argument.

```javascript
$ node index.js

```
## Basic Components

### Globals
Like the Browser, Node.js comes with some practical globals for us to use in our applications.

### Modules
A module is a reusable chunk of code that has its own context. That way modules can't interfere with or polute the global scope.

You can think of them like lego blocks that you can create, import, and share.


By default, Node.js uses common js modules. With newer versions of Node.js we can now take advantage of ES6 modules. To opt into using this syntax, you can use the .mjs extension instead of .js. We'll be using the ES6 module syntax going forward as they are the standard now with browsers adding support now.

Now, let's create our first module. The only thing we have to do is expose some code in one for our JavaScript files. We can do that with the export keyword.

```javascript
// utils.js
export const action = () => {

}

export const run = () => {

}
```

```javascript
// app.js

import { action, run } from './utils'
```

Few things happening here. Let's look at the `utils.js` file. Here we're using the `export` keyword before the variable declartion. This creates a named export. With the name being whatever the variable name is. In this case, a function called `action`. Now in `app.js`, we `import` the action module from the utils file. The path to the file is relative to the file you're importing from. You also have to prefix your path with a `'./'`. If you don't, Node will think you're trying to import a built in module or npm module. Because this wa a named export, we have to import with brackets `{ action, run }` with the exact name of the modules exported. We don't have to import every module that is exported.

Usually if you only have to expose one bit of code, you should use the `default` keyword. This allows you to import the module with whatever name you want.

```javascript
// utils.js
default export function () {
  console.log('did action')
}
```

```javascript
// app.js
import whateverIWant from './utils'
```

You can read more about the module syntax on the [Node.js docs](https://nodejs.org/api/packages.html).



### File System

### Error Handling

## Packages

### Local Packages & NPM

### Finding & Installing Packages

### Using NPM Packages

### Running NPM Scripts

## CLI

### Setup CLI with Node.js

## Creating Servers

### Testing API with HTTPie

### Server API with Express

### Dynamic Routes in Express

## Unit Tests

### Vanila Unit Testss

### Asynchronous Tests

### Debugging

## Deployment

### Deployment Packages

### Deployment Servers