component-app-seed
==================

Simple seed project for [component(1)](http://component.io/) based apps.  

## Quickstart

1. Clone or download the repo
2. Change the project name, description, version etc. in `component.json`
3. Run `make` and open your browser to `index.html`. You should see "works!" in red.

## Workflow

A few assumptions:

1. `index.html` is your landing page and `lib/boot/` is your app's entry point component.
2. All local components will be created under `lib/`
3. Each local component will define it's own dependencies  

### Local components

To create a new local component:

    $ component create -l lib/<component-name>

To require it from another local component, add `<component-name>` to the `local` array in `component.json` of the requiring component.

### Third party components

Search for components:

    $ component search <component-name>

Add the component `<github-username>/<component-name>` to the local component's `dependencies` object with the value being the version number or `*` for latest.  

_Note that all dependencies will be installed in the root directory's `component/`_

### Make commands

Build for development:

    $ make

For a nicer workflow install [watch(1)](https://github.com/visionmedia/watch) to build everytime a source file changes:

    $ watch make

Install dependencies:

    $ make components
    
To create a production build you need to install [component-minify](https://github.com/gingkoapp/component-minify) and run:

    $ make minify

To clean the working directory from build files (useful for updating components):

    $ make clean

## Example apps using this

* [GuessHub.io](https://github.com/max99x/guesshub/)
* [debugjs.com](https://github.com/amasad/debugjs.com)
* [learnable-programming-demo](https://github.com/amasad/learnable-programming-demo)
