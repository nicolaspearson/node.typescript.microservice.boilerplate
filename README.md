# Node TypeScript Microservice Boilerplate

A simple boilerplate for building Node.js microservices with TypeScript. Put your typescript code inside `./src` folder and you are ready to go!

## Included

* VS Code debugger configs in .vscode folder
* Recommended Dockerfile for secure nodejs container
* A tsconfig.json file for the [typescript compiler](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)
* A strict tslint.json file to apply [tslint](https://palantir.github.io/tslint/)

## Getting Started

```
# Clone the repository
git clone https://github.com/nicolaspearson/node.typescript.microservice.boilerplate.git
cd node.typescript.microservice.boilerplate

# Remove reference to the original project
rm -rf .git && git init && npm init

# Install development dependencies
npm install

# Start the development server
npm run dev
```

## Included npm scripts

Run these commands from the project folder with `npm run "script-name"`:

* `dev`: runs the development server with [nsp security check](https://nodesecurity.io/), [ts linter](https://palantir.github.io/tslint/) and `nodemon` watching `.ts` files inside `./src` folder and auto-restarts on save.
* `build`: builds all .ts files from `./src` folder to `./build`
* `lint`: lints all source code using `tslint`
* `security-check`: checks installed dependencies against node security database
* `share`: runs development server and exposes it with [localtunnel](https://localtunnel.github.io/www/)
* `start`: starts the production server. Run `build` command to compile TS to JS before running this.
* `update`: easily check for updates and update all dependencies

## Debugging
> Warning: This project uses new V8 [inspect protocol](https://nodejs.org/api/debugger.html) so you have to use at least Node.js 7.7.4 if you want to use the included debugger settings.

#### Steps:
* Start the dev server with `npm run dev`
* Start debugging in one of two ways:
  * Use the provided debug URL in Chrome
  * Use VS Code included (inside .vscode folder) `attach` config (best debugging experience)

## Docker Support

This project uses Node.js best practices and creates a dummy user to start the node process, instead of using the root user.

```
# From the project root directory, build the docker image
docker build -t my-project-name .

# Run the image in a docker container
docker run -p PORT:PORT my-project-name
```
