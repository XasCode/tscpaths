> This is a fork of [joonhocho/tscpaths](https://github.com/joonhocho/tscpaths) that adds the --silent option.

# tscpaths

Replace absolute paths to relative paths after typescript compilation (tsc) during compile-time.

[![npm version](https://badge.fury.io/js/@herbcaudill/tscpaths.svg)](https://badge.fury.io/js/@herbcaudill/tscpaths)
[![Dependency Status](https://david-dm.org/herbcaudill/tscpaths.svg)](https://david-dm.org/herbcaudill/tscpaths)
[![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org)

## Comparison to [tsconfig-paths](https://github.com/dividab/tsconfig-paths)

\+ Compile time (no runtime dependencies)

## Getting Started

First, install tscpaths as devDependency using npm or yarn.

```sh
npm install --save-dev @herbcaudill/tscpaths
# or
yarn add -D @herbcaudill/tscpaths
```

## Add it to your postbuild script in package.json

```json
"scripts": {
  "build": "tsc --project tsconfig.json",
  "postbuild": "tscpaths -p tsconfig.json -s ./src -o ./out --silent",
}
```

### Options

| flag         | description                                        |
| ------------ | -------------------------------------------------- |
| -p --project | project configuration file (tsconfig.json)         |
| -s --src     | source code root directory                         |
| -o --out     | output directory of transpiled code (tsc --outDir) |
| --silent     | silence the console output                         |

You need to provide -s (--src) and -o (--out), because it's hard to predict source and output paths based on tsconfig.json.
