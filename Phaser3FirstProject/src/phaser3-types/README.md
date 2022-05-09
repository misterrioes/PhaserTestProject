# Phaser3 Auto-Typer
This project is a CI job to automatically build type definitions for Phaser3.

## Usage
Kinda awkward because we aren't a `@types` module.

`npm install phaser@3.X.Y`

`npm install @ebutler/phaser3-types@~3.X.0`

Now `node_modules/@ebutler/phaser3-types/index.d.ts` can be copied to any folder in your project (like `typings/`) and you'll have the newest typedefs.

## Semver Huh?
This repo will follow phaser3 on MAJOR.MINOR but will reserve PATCH for its own modifications that might rebuild the same MAJOR.MINOR typings from phaser.

i.e. Phaser bumps to 5.4.0, this repo should publish 5.4.0
Phaser then bumps to 5.4.1, this repo should publush 5.4.1
This repo needs to modify part of its process that doesn't affect types, no version change.
This repo needs to modify part that DOES affect the types, bump to 5.4.2.

Consumers of this project should always feels confident `npm install @ebutler/phaser3-types@~X.Y.0`

## How? 
This pulls the latest Phaser repo and Phaser3-docs repo, then runs the typescript generator, then publishes it to `npm` under `@ebutler/phaser3-types` module name.