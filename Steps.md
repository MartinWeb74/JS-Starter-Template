## Step 1

Choose a code editor.
VS Code has the most features for team working. Use editorConfig to generate rules that all user will follow. Atom is another great code editor to use.

## Step 2

Choose a JS Package Manager.
npm is the most popular one these days. Other package managers to mention: JSPM, Jam, Bower, Volo.
Create and setup a package.json file: [https://docs.npmjs.com/files/package.json](https://docs.npmjs.com/files/package.json)
Example file: [bit.ly/jsdevpackagejson](bit.ly/jsdevpackagejson)
Install dependencies with 'npm install' inside the projects folder.

## Step 3

Packages security scan. use: [https://nodesecurity.io/](https://nodesecurity.io/) also can use: [https://retirejs.github.io/retire.js/](https://retirejs.github.io/retire.js/)
This can be ran manually or it can added to the 'npm start' script.
Install the 'nsp' tool globally with: 'npm install -g nsp'
Then run it from inside the project with: 'nsp check'

## Step 4

Configure a development web server.
Some web server packages to mention:
**http-server**: super simple, no configuration needed, run it with one line of code.
**live-server**: very simple but with a few more features.
**express**: very robust, production ready level.
**webpack**: built in webpack, very robust.
**browsersync**: different feature => creates a dedicated IP for sharing on LAN, also it has live-sync meaning you can open the app on many browsers and see changes on all simultaneously.
Setting up 'express': [https://expressjs.com/](https://expressjs.com/)
Create a new folder called 'buildScripts', inside this create a file called 'srcServer.js', fill the settings and run: 'node buildScripts/srcServer.js'

## Step 4 B

Ways to share work on local network.
Some packages: **localtunnel**, **ngrok**, **surge**, **now**.
Example with localtunnel: run 'npm install localtunnel -g' to install the package globally.
Run the app as previouslly.
Open a second terminal (to keep the server running)
Use 'lt --port 3000 --subdomain martin'

## Step 5

Automation Tools.
Most popular tools: **Grunt, Gulp, npm Scripts**.
GulpJS: [https://gulpjs.com/](https://gulpjs.com/)
npm Scripts, simpler to use, good documentation
Use the 'Scripts' section of the package.json file to add scripts to run.
Examples:
"prestart": "node buildScripts/startMessage.js",
"start": "node buildScripts/srcServer.js"
Tasks can be ran in parallel with 'npm-run-all'
Use 'npm start -s' to run the server and -s silences the extra cmd line outputs.

## Step 6

Transpiling.
Tranpilers options: **Babel, TypeScript, Elm.**
[https://babeljs.io/](https://babeljs.io/)
[http://elm-lang.org/](http://elm-lang.org/)
Configuring Babel:
Simply create a file named '.babelrc' on the root folder and add the following:

    {
      "presets": [
        "latest"
       ]
    }

On the scripts section of package.json change 'node' for 'babel-node' to compile the files at runtime.

## Step 7:

Bundling.

### Modules Formats

- IIFE
- Asynchronous Module Definition (AMD)
- CommonJS (CJS)
- Universal Module Definition (UMD)
- ES6 Modules

ES6 Modules is the current best practice way to encapsulate code.
Example:

    import jQuery from 'jquery'

Bundlers to consider:

- Browserify
- Webpack
- Rollup
- JSPM

[https://webpack.js.org/](Webpack) is the most popular today. Bundles more than just JS; it imports CSS, images, etc. It includes a hot-reloading web server, which display changes and updates automatically.

[https://rollupjs.org/guide/en](Rollup) uses "tree shaking" meaning it removes all unnecessary code from the bundle, creating faster code output.