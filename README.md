# iohook

[![Build status](https://ci.appveyor.com/api/projects/status/2ntnlh6k953he5is?svg=true)](https://ci.appveyor.com/project/Djiit/iohook)
[![Build Status](https://travis-ci.org/wilix-team/iohook.svg?branch=master)](https://travis-ci.org/wilix-team/iohook)
[![Gitter chat](https://badges.gitter.im/gitterHQ/gitter.png)](https://gitter.im/iohookjs/Lobby)
[![NPM version](https://img.shields.io/npm/v/iohook.svg)](https://www.npmjs.com/package/iohook)

# About this fork

This fork has the following changes:
* Release build for ARM (Node versions 8, 10, 12 and 13)
* Tiny change to 'install.js' to reference 'npm run build' instead of 'npm run compile' in a console.log message
* Added comments on how to build for ARM (Raspberry Pi, Raspbian Buster Lite)
* Adjusted installer script (install.js) to reference this repo
* Fixed a segmentation violation when no keyboards were found (see https://github.com/wilix-team/iohook/issues/207)

# Building this module for Raspberry Pi

To build iohook for RPi (and maybe other platform) the following must be done:

* Clone this repo
* Install dependencies:
    - `sudo apt install libx11-dev libxtst-dev libxt-dev libx11-xcb-dev libxkbcommon-dev libxkbcommon-x11-dev autoconf libtool libxinerama-dev libxkbfile-dev`
* Clear old dependencies and install NAN
    - `rm package-lock.json`
    - `npm install nan`
* Build iohook.node
    - `npm run build`

To build a release:
* `npm install mkdirp archiver cmake-js`
* For Node 8:
   - `node build.js --no-upload --runtime node --version 8.17.0 --abi 57`
   - Resulting build will be in prebuilds folder, such as `./prebuilds/iohook-v0.6.5-node-v72-linux-arm.tar.gz`
* For Node 10:
   - `node build.js --no-upload --runtime node --version 10.20.2 --abi 64`
   - Resulting build will be in prebuilds folder, such as `./prebuilds/iohook-v0.6.5-node-v64-linux-arm.tar.gz`
* For Node 12:
   - `node build.js --no-upload --runtime node --version 12.16.2 --abi 72`
   - Resulting build will be in prebuilds folder, such as `./prebuilds/iohook-v0.6.5-node-v72-linux-arm.tar.gz`
* For Node 13:
   -  `node build.js --no-upload --runtime node --version 13.12.0 --abi 79`
   - Resulting build will be in prebuilds folder, such as `./prebuilds/iohook-v0.6.5-node-v79-linux-arm.tar.gz`


## About

Node.js global native keyboard and mouse listener.

This module can handle keyboard and mouse events via native hooks inside and outside your JavaScript/TypeScript application.

Found a bug? Have an idea? Feel free to post an [issue](https://github.com/wilix-team/iohook/issues) or submit a [PR](https://github.com/wilix-team/iohook/pulls).

**Check out the [documentation](https://wilix-team.github.io/iohook).**

## Platform support

- Versions >= 0.6.0 support only officially supported platforms versions.
- Versions 0.5.X are the last to support Electron < 4.0.0
- Versions 0.4.X are the last to support for Node < 8.0 and Electron < 2.0.0

## Installation

iohook provides prebuilt version for a bunch of OSes and platforms.

```bash
npm install iohook --save # or yarn add iohook
```

## FAQ

Q. _Does this module require Java ?_

A. No, this module doesn't require Java (like jnativehook) or any other runtimes.

Q. _Is iohook compatible with Node/Electron version X.Y.Z ?_

A. We try to match the currently supported version of both [Node](https://nodejs.org/en/about/releases/) and [Electron](https://electronjs.org/docs/tutorial/support#currently-supported-versions).

## Apps

Are you using iohook in your project ? Please tell us in a [PR](https://github.com/wilix-team/iohook/pulls) so we an add it to the list !

- [Cortex](https://crtx.gg/)

## Contributors

Thanks to _kwhat_ for the [libuiohook](https://github.com/kwhat/libuiohook) project and [ayoubserti](https://github.com/ayoubserti) for the first iohook prototype.

- [vespakoen](https://github.com/vespakoen) (prebuild system implementation)
- [matthewshirley](https://github.com/matthewshirley) (Windows prebuild fix)
- [djiit](https://github.com/djiit) (project & community help)
- [ezain](https://github.com/eboukamza) (add feature enable/disable mouse click propagation)
- [anoadragon453](https://github.com/anoadragon453) (electron 4+ support)
- All the other contributors. Feel free to extend this list !
