# Olden

Olden has been born out of necessity. For more than 2 years I've been using MacOS as my primary
OS and I got used to a lot of MacOS specific tools and apps. One of those apps was CopyClip 2, which
is an amazing clipboard manager, and for months I couldn't imagine my life without it, but not long ago
things have changed. I was forced to work on Windows and I had to adopt to the new setup.

Don't get me wrong, I really like Windows 10, but I miss MacOS specific tools on it. I tried to
find CopyClip 2 alternative, but all Windows clipboard managers are either outdated or too
complicated, or doesn't have the same feel to them as CopyClip does. So I made a decision to build
my own clipboard manager that would work on every platform I might end up working on and so Olden was born.

Olden is built using the amazing Electron package from GitHub and while still in development it has
not only become an important tool for me on Windows but also replaced CopyClip on MacOS.

![Olden preview](https://raw.githubusercontent.com/aigarsdz/olden/master/assets/screenshots/Screen%20Shot%202016-09-09%20at%202.25.07%20AM.png)

## Installation

Go to [releases](https://github.com/aigarsdz/olden/releases) section and download the file that fits
your OS. For MacOS it's dmg, for Windows - zip. I haven't provided a Linux package because I need to do more
testing and research on it, but it will be available in the next release. I also haven't made a Windows
installer because it requires a code signing certificate, so I postponed it for a while. I will add
it alongside auto updater at some point.

## Usage

I have borrowed a lot from CopyClip. Right now you can open it using `Alt+Space` keyboard shortcut.
Use left/right keys to navigate through the history, up/down keys to highlight a specific item and
enter key to select it.

A demo is coming soon.   

## Development

You will have to have Node and NPM installed in order to develop Olden.

In most of Node projects you can just run `npm i` to install all the dependencies, but the
project structure of Olden is a bit more complicated and it uses 2 package.json files, therefore,
to set up all the pependencies in the correct way, run `npm run bootstrap`. It will install
[electron-prebuilt](https://github.com/electron-userland/electron-prebuilt "electron-userland/electron-prebuilt: Install precompiled versions of Electron using npm") globally, so you could use `electron` command-line utility (it's also required by
`npm start`), and [appdmg](https://github.com/LinusU/node-appdmg "LinusU/node-appdmg: Generate your app dmgs"),
[archiver](https://github.com/archiverjs/node-archiver "archiverjs/node-archiver: a streaming interface for archive generation"), [electron-packager](https://github.com/electron-userland/electron-packager "electron-userland/electron-packager: Package and distribute your Electron app with OS-specific bundles (.app, .exe etc) via JS or CLI") and
[rimraf](https://github.com/isaacs/rimraf "isaacs/rimraf: A `rm -rf` util for nodejs") locally as development
dependencies. After that run `bower install` to install [Vue.js](https://vuejs.org "vue.js"), which is used for rendering.

When you're done making your changes to the project, run `npm run build` to copy all the necessary
files to the app folder. App packaging is done using npm run `package_macos` for MacOS and
`npm package_win` for Windows.
