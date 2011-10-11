# node-jshint

A command line interface and npm package for jshint.

## Install

To use jshint from any location (for npm v1.x) you need to install using the global (-g) flag. 

    npm install -g jshint

## Usage

The command line interface looks like this.

    jshint path path2 [options]

You can also require JSHint itself as a module.

    var jshint = require('jshint');

Note: If you are using npm v1.x be sure to install jshint locally (without the -g flag) or link it globally.

## Text Editor Plugins

* [gedit-node-jshint](https://github.com/niftylettuce/gedit-node-jshint) - Simply use CTRL+J in gedit to run JSHint using `node-jshint`.
* [vim syntastic](https://github.com/scrooloose/syntastic) - Run node-jshint at each file save.

## Custom Reporters

Specify a custom reporter module (see example/reporter.js).

    --reporter path/to/reporter.js

Use a jslint compatible xml reporter.

    --jslint-reporter

Show additional non-error data generated by jshint (unused globals etc).

    --show-non-errors

## Custom Options

Specify custom lint options (see [example/config.json](https://github.com/jshint/node-jshint/blob/master/example/config.json)).

    --config path/to/config.json

Note: This bypasses any .jshintrc files.

## Default Options

The CLI uses the default options that come with JSHint. However, if it locates a .jshintrc file in your home directory (~/) it will use those options first.

## Per Directory Options

If there is a .jshintrc file in the current working directory, any of those options will take precedence over (or be merged with) any options found in the ~/.jshintrc file (if it exists).

## Ignoring Files and Directories

If there is a .jshintignore file in the current working directory, then any directories or files will be skipped over.

Note: Pattern matching uses fnmatch, with the FNM_PATHNAME & FNM_CASEFOLD [flags](https://github.com/isaacs/node-glob/blob/master/README.md). When there is no match, it performs a left side match (when no forward slashes present and path is a directory).

## Installing dependencies for development

    ./configure

## Build Commands

    jake -T
