---
title: 'HowTo: Set Up an Offline IBM MobileFirst 8.0 Development Environment'
date: 2016-04-01
tags:
- MobileFirst_Platform
- Offline
- Setup
- Development_Environment
author:
  name: Danny Cao
---
## Overview
IBM MobileFirst Platform Foundation supports offline development, but requires modified installation steps as detailed below. For additional development tutorials and standard installation instructions refer to the [IBM MobileFirst Platform Foundation 8.0 Tutorials]({{site.baseurl}}/tutorials/en/foundation/8.0/). The following prerequisite programs will need an online connection to download before transferring to an offline development machine for installation.

## Prerequisites
* Cordova
    * [cordova-cli (6.0.0+)](https://www.apache.org/dist/cordova/tools/)
    * [Cordova Platforms](https://www.apache.org/dist/cordova/platforms/)
        * cordova-android (5.0.0+)
        * cordova-ios (4.0.1+)
        * cordova-windows (4.2.0+)
* [Java (JDK 1.7+)](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html): For running a local development server
* [Maven (3.3.9+)](https://maven.apache.org/download.cgi): For adapter development
* [MobileFirst Platform Foundation Development Kit (8.0+)]({{site.baseurl}}/tutorials/en/foundation/8.0/setting-up-your-development-environment/mobilefirst-development-environment/#mobilefirst-platform-foundation-development-kit): Includes the MobileFirst Server & MobileFirst Operations Console, MobileFirst Developer Command-line Interface (CLI), MobileFirst client SDKs and MobileFirst adapter tooling.
* [Node.js (0.12.0+)](https://nodejs.org/en/download/releases/): For the MobileFirst CLI and Cordova

For additional offline platform specific development prerequisites see the [tutorial page]({{site.baseurl}}/tutorials/en/foundation/8.0/setting-up-your-development-environment/) for more instructions.

## Cordova Preparation
The downloaded cordova-x.y.z.tgz file has third party dependencies that are not packaged with the archive and requires an online connection to first cache those dependencies before it can be moved to an offline machine for installation. See [NPM issue #4210](https://github.com/npm/npm/issues/4210) for more information and suggested workarounds for offline npm installs or use [npmbox](https://github.com/arei/npmbox). We suggest the following workaround:

While still online

1. Install Node.js on the online machine
2. Change directory to where you downloaded cordova-x.y.z.tgz and run `npm --cache ./.cache install cordova-x.y.z.tgz` to generate and cache the dependencies needed
3. Zip the new generated .cache folder and move this file along with the cordova-x.y.z.tgz file to the offline machine

On the offline machine

1. Unzip the .cache folder
2. Run `npm install --cache ./.cache cordova-x.y.z.tgz -g` to install cordova globally using the previously generated cache (Note: this may take a while)

The cordova command is now available for use. For any other packages that you may run into issues installing on an offline machine, the above caching method is viable as well.

## Installation
Once all of the above files are downloaded, move them to an offline machine for installation. Cordova and the associated cordova platforms as well as the MobileFirst CLI will need to be installed after Node.js has been installed.

## MobileFirst Operations Console
The MobileFirst Development Kit installer includes snapshot downloads for various development artifacts (listed above in Prerequisites) downloadable via the MobileFirst Operations Console downloads page.

![downloads]({{site.baseurl}}}}/tutorials/en/foundation/8.0/setting-up-your-development-environment/console/downloads.png)

See the [MobileFirst Operations Console Tutorial]({{site.baseurl}}/tutorials/en/foundation/8.0/setting-up-your-development-environment/console/) for more information on accessing and navigating the console.

## MobileFirst CLI
To use the CLI first download if from the MobileFirst Operations Console via the instructions above and then install it by running `npm install -g mfpdev-cli.tgz`.