---
layout: post
author:
    name: Steve Gill
    url: https://twitter.com/stevesgill
title:  "Tools Release: March 02, 2015"
categories: news
tags: release tools
---
New versions of cordova tools are now live!

* [cordova-lib@4.3.0](https://www.npmjs.org/package/cordova-lib)
* [cordova@4.3.0](https://www.npmjs.org/package/cordova)
* [plugman@0.23.0](https://www.npmjs.org/package/plugman)
* [cordova-js@3.8.0](https://www.npmjs.org/package/cordova-js)

To update your tools:

  * If you have `cordova` installed:

        npm install -g cordova

  * If you have `plugman` installed:

        npm install -g plugman

Release highlights:

* You can manage plugin and platform versions using the `--save` command when adding platforms and plugins to your project. Ex. `cordova platform add android --save`. This should make it easier developing cordova projects among a team.
* Plugin authors can use the new command `plugman createpackagejson <plugin_path>` to add a package.json file to their plugins. We are going to be doing a blog post soon about transitioning plugins to npm with some more details. Stay tuned. 

# Changes include:
<!--more-->

## Platform updates
When adding these platforms to your project, the following versions are now used by default.
These platform versions were released recently, and the tools' defaults were updated:

* [Cordova iOS 3.8.0](http://cordova.apache.org/announcements/2015/02/25/cordova-ios-3.8.0.html)
* [Cordova Windows 3.8.0]()
* [Cordova Android 3.7.1](http://cordova.apache.org/announcements/2015/02/06/cordova-android-3.7.1.html)

## cordova-lib
* updated pinned versions of ios to 3.8.0 and android to 3.7.1
* [CB-8524](https://issues.apache.org/jira/browse/CB-8524) Switched to the latest Windows release
* changed createpackage.json keyword to ecosystem:cordova
* [CB-8448](https://issues.apache.org/jira/browse/CB-8448) add support for activities
* [CB-8482](https://issues.apache.org/jira/browse/CB-8482) rename: platformId -> platformName
* [CB-8482](https://issues.apache.org/jira/browse/CB-8482): Update engine syntax within config.xml
* Organize save logic some more
* --save flag for plugins
* fix for test after prepare changes
* restore plugins and platforms on prepare
* [CB-8472](https://issues.apache.org/jira/browse/CB-8472) Can't find config.xml error installing browser platform after plugin.  (close #167)
* [CB-8469](https://issues.apache.org/jira/browse/CB-8469) android: Call into platform's build.js after `plugin add` so that Android Studio will work without needing an explicit command-line build first
* [CB-8123](https://issues.apache.org/jira/browse/CB-8123) Fix JSHINT issue.
* [CB-8123](https://issues.apache.org/jira/browse/CB-8123) Fix path handling so tests work on any platform.
* [CB-8123](https://issues.apache.org/jira/browse/CB-8123) Rename further windows platform related files.
* [CB-8123](https://issues.apache.org/jira/browse/CB-8123) Rename windows platform related files.
* [CB-8123](https://issues.apache.org/jira/browse/CB-8123) Plugin references can target specific windows platforms.
* [CB-8420](https://issues.apache.org/jira/browse/CB-8420) Make `cordova plugin add FOO` use version from config.xml (close #162)
* [CB-8239](https://issues.apache.org/jira/browse/CB-8239) Fix `cordova platform add PATH` when PATH is relative and CWD != project root
* [CB-8227](https://issues.apache.org/jira/browse/CB-8227) CB8237 [CB-8238](https://issues.apache.org/jira/browse/CB-8238) Add --save flag and autosave to 'cordova platform add', 'cordova platform remove' and 'cordova platform update'
* [CB-8409](https://issues.apache.org/jira/browse/CB-8409) compile: bubble failures
* [CB-8239](https://issues.apache.org/jira/browse/CB-8239) Fix "platform update" should ignore `<cdv:engine>` (close #159)
* [CB-8390](https://issues.apache.org/jira/browse/CB-8390) android: Make `<framework custom=false>` work with Gradle
* [CB-8416](https://issues.apache.org/jira/browse/CB-8416) updated plugman publish to temporarily rename existing package.json files
* [CB-8416](https://issues.apache.org/jira/browse/CB-8416): added `plugman createpackagejson .` command to create a package.json from plugin.xml
* [CB-6973](https://issues.apache.org/jira/browse/CB-6973) add spec-plugman to npm run jshint
* [CB-6973](https://issues.apache.org/jira/browse/CB-6973) fix spec-plugman jshint failures
* [CB-6973](https://issues.apache.org/jira/browse/CB-6973) have base rules in jshintrc for spec-plugman
* [CB-8377](https://issues.apache.org/jira/browse/CB-8377) Fixed <runs> tag parsing (close #156)
* [CB-5696](https://issues.apache.org/jira/browse/CB-5696) find ios project directory using the xcode project file (close #151)
* [CB-8373](https://issues.apache.org/jira/browse/CB-8373) android: Add gradle references to project.properties rather than build.gradle
* [CB-8370](https://issues.apache.org/jira/browse/CB-8370) Make "plugman publish" without args default to CWD
* Fix publish type-error introduced in recent commit 15adc1b9fcc069438f5
* [CB-8366](https://issues.apache.org/jira/browse/CB-8366) android: Remove empty `<framework>` directory upon uninstall
* [CB-6973](https://issues.apache.org/jira/browse/CB-6973) Enable JSHint for spec-cordova
* [CB-8239](https://issues.apache.org/jira/browse/CB-8239) Add support for git urls to 'cordova platform add' (close #148)
* [CB-8358](https://issues.apache.org/jira/browse/CB-8358) Add `--link` for `platform add` and `platform update`
* [CB-6973](https://issues.apache.org/jira/browse/CB-6973) remove base rules from individual files in src
* [CB-6973](https://issues.apache.org/jira/browse/CB-6973) have base rules in .jshintrc file
* Add shims to undo breaking change in a20b3ae3 (didn't realize PluginInfo was exported)
* [CB-8354](https://issues.apache.org/jira/browse/CB-8354) Add --link support for iOS source and header files
* Make all ad-hoc plugin.xml parsing use PluginInfo instead
* Make all usages of PluginInfo use PluginInfoProvider instead
* Add PluginInfoProvider for better caching of PluginInfo
* [CB-8284](https://issues.apache.org/jira/browse/CB-8284) revert npm dependency due to issues with registry
* [CB-8223](https://issues.apache.org/jira/browse/CB-8223) Expose config.xml in the Browser platform (close #149)
* [CB-8168](https://issues.apache.org/jira/browse/CB-8168) --list support for cordova-lib (close #145)
* [Amazon] Improve error message when `<source-file>` is missing `target-dir`
* refactor: Make addUninstalledPluginToPrepareQueue take pluginId rather than dirName
* Chnage plugman test plugins to have IDs as directory names

## cordova-cli
* docs update for plugin --save
* Grunt "retire" task added (close #204)
* [CB-8439](https://issues.apache.org/jira/browse/CB-8439) Fix 'cordova platform update' documentation to include `<plat-spec>` (close #208)
* [CB-8379](https://issues.apache.org/jira/browse/CB-8379) Have --version print out cordova-lib version if it's not the same as CLI's version
* [CB-8211](https://issues.apache.org/jira/browse/CB-8211), [CB-8358](https://issues.apache.org/jira/browse/CB-8358) Update `--link` help text
* [CB-8168](https://issues.apache.org/jira/browse/CB-8168) --list support for CLI (close #205)
* [CB-8314](https://issues.apache.org/jira/browse/CB-8314) Speed up Travis CI (close #207)
* [CB-8301](https://issues.apache.org/jira/browse/CB-8301) Added CI configuration files (close #206)
* [CB-8227](https://issues.apache.org/jira/browse/CB-8227) [CB-8237](https://issues.apache.org/jira/browse/CB-8237) [CB-8238](https://issues.apache.org/jira/browse/CB-8238) Add --save option to 'cordova platform add', 'cordova platform remove' and 'cordova platform update'
* Add coverage/ to .npmignore
* [CB-5316](https://issues.apache.org/jira/browse/CB-5316) Spell Cordova as a brand unless it's a command or script
* [CB-7950](https://issues.apache.org/jira/browse/CB-7950) CLI make CordovaCliCreate.prototype.run vaguely correct
* [CB-7739](https://issues.apache.org/jira/browse/CB-7739) document installing specific version of platforms
* [CB-7950](https://issues.apache.org/jira/browse/CB-7950) CLI create.js misspells parseConfig

## cordova-js
* [CB-8378](https://issues.apache.org/jira/browse/CB-8378) android: Deleted hidekeyboard & showkeyboard events
* android: Use correct plugin name for navigator.app exec() calls
* [CB-8314](https://issues.apache.org/jira/browse/CB-8314) Speed up Travis CI (close #102)
* [CB-8302](https://issues.apache.org/jira/browse/CB-8302) Added `npm test` script
* [CB-8158](https://issues.apache.org/jira/browse/CB-8158) fixed symbolList require
* [CB-8300](https://issues.apache.org/jira/browse/CB-8300) Added CI configuration files
* [CB-8298](https://issues.apache.org/jira/browse/CB-8298) android: Execute exec callbacks within their own stack frames
* [CB-8210](https://issues.apache.org/jira/browse/CB-8210) Remove unused onDestroy channel (close #99)
* Fixed callbackFromNative method

## plugman
* [CB-8416](https://issues.apache.org/jira/browse/CB-8416) added `plugman createpackagejson .` command to generate a package.json file from plugin.xml
* [CB-8370](https://issues.apache.org/jira/browse/CB-8370) Update documentation for `plugman publish` without args

## Pinned Platform Versions for Cordova CLI 4.2.0

* Cordova Amazon-FireOS: 3.6.3
* Cordova Android: 3.7.1
* Cordova BlackBerry10: 3.7.0
* Cordova Browser: 3.6.0
* Cordova FirefoxOS: 3.6.3
* Cordova iOS: 3.8.0
* Cordova Ubuntu: 4.0.0
* Cordova Windows: 3.8.0
* Cordova WP8: 3.7.1
