# Electron Release Server
A node web server which serves & manages releases of the your [Electron](http://electron.atom.io) App, and is fully compatible with [Squirrel](https://github.com/Squirrel) Auto-updater (which is built into Electron).

_Note: while I market this as a release server for Electron applications, it would work for **any application using Squirrel**._

If you host your project on your Github and do not need a UI for your app, then [Nuts](https://github.com/GitbookIO/nuts) is probably what you're looking for. Otherwise, you're in the same boat as I was, and you've found the right place!

## Features
- :sparkles: Awesome release management interface powered by [AngularJS](https://angularjs.org)
    - Authenticates with LDAP, easy to modify to another authentication method if needed
- :sparkles: Store assets on server disk, or Amazon S3 (with minor modifications)
    - Use pretty much any database for persistence, thanks to [Sails](http://sailsjs.org) & [Waterline](http://waterlinejs.org)
- :sparkles: Simple but powerful download urls
    - `/download/latest`
    - `/download/latest/:os`
    - `/download/:version`
    - `/download/:version/:os`
    - `/download/channel/:channel`
    - `/download/channel/:channel/:os`
- :sparkles: Support pre-release channels (`beta`, `alpha`, ...)
- :sparkles: Auto-updates with [Squirrel](https://github.com/Squirrel)
    - For Mac using `/update?version=<x.x.x>&platform=osx`
    - For Windows using Squirrel.Windows and Nugets packages
- :sparkles: Serve the perfect type of assets: `.zip` for Squirrel.Mac, `.nupkg` for Squirrel.Windows, `.dmg` for Mac users, ...
- :sparkles: Release notes endpoint
    - `/notes/:version`

## Deploy it / Start it

[Follow our guide to deploy Electron Release Server](docs/deploy.md).

## Auto-updater / Squirrel

This server provides an endpoint for [Squirrel auto-updater](https://github.com/atom/electron/blob/master/docs/api/auto-updater.md), it supports both [OS X](docs/update-osx.md) and [Windows](docs/update-windows.md).

## Documentation

[Check out the documentation](docs/) for more details.

## Building Releases
I highly recommend using [electron-builder](https://github.com/loopline-systems/electron-builder) for packaging & releasing your applications. Once you have built your app with that, you can upload the artifacts for your users right away!

## Credit
This project has been built from the SailsJs base up by Arek Sredzki, with inspiration from [nuts](https://github.com/GitbookIO/nuts).

I've also borrowed some of their documentation! Thanks!
