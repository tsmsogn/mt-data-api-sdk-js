This SDK is a toolkit to access to Movable Type's DataAPI.

Some files generated by this product are parts of the Movable Type.

# Using as a library for Node.js

## Installation

```
  npm install git://github.com/movabletype/mt-data-api-sdk-js.git
```

or

```
  npm install <downloaded tarball>
```

## Usage

```
var MT = {
    DataAPI: require("mt-data-api-sdk")
};
var api = new MT.DataAPI({
  baseUrl:  "http://example.com/mt/mt-data-api.cgi",
  clientId: "node"
});
var credential = {
  username: "USER_NAME",
  password: "PASSWORD",
  remember: true
};

// Session information will be stored to "$HOME/.mt-data-api.json" by default.
api.authenticate(credential, function(response) {
  if (! response.error) {
    api.listEntries(2, {status: "Draft"}, function(response) {
      // Do stuff
    });
  }
});
```

# Development

## Prerequisites
Installation depends on [node](http://nodejs.org/), [npm](https://npmjs.org/), and [grunt-cli](http://gruntjs.com/)

To install node, see http://nodejs.org/ (If you are using Mac, you can install node via [homebrew](http://mxcl.github.io/homebrew/))

Then, you can install grunt-cli with npm like the following. When you have some error in installation, try sudo.

```
  [sudo] npm install -g grunt-cli
```

## Installation
`git clone git@github.com:movabletype/mt-data-api-sdk-js`, and move the directory you cloned, then execute the following command

```
  npm install
```

## Building for develop
grunt dev task generate scripts in lib and dist directory from src directory, and run the dependant tasks

```
  grunt dev
```

## Building for production
grunt build task generate optimized scrips in dist directory

```
  grunt build
```

# License
The MIT License (MIT)
