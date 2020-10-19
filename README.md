# cordova-plugin-firebase-dynamiclinks<br>[![NPM version][npm-version]][npm-url] [![NPM downloads][npm-downloads]][npm-url]
> Cordova plugin for [Firebase Dynamic Links](https://firebase.google.com/docs/dynamic-links/)

## This plugin is compatible to work with cordova-plugin-firebase and supports iOS 12 fix from author georgski

## NOTE

By default `GoogleToolboxForMac` and `nanopb` has been disabled to avoid conflicts with [Push Plugin](https://github.com/phonegap/phonegap-plugin-push)
. In order to make them available for your project, simply uncomment `line 107-108` in `plugin.xml`. This is only needed if you are using [Push](https://github.com/phonegap/phonegap-plugin-push) or any other plugin which already includes these two dependencies.
 
## Installation

    cordova plugin add cordova-plugin-firebase-dynamiclinks --save --variable APP_DOMAIN="example.com" --variable PAGE_LINK_DOMAIN="example.page.link"

Use variable `APP_DOMAIN` specify web URL where your app will start an activity to handle the link.

Use variable `PAGE_LINK_DOMAIN` specify your `*.page.link` domain.

Use variable `FIREBASE_DYNAMIC_LINKS_VERSION` to override dependency version on Android.

## Supported Platforms

- iOS
- Android

Firebase Dynamic Links SDK has an [unresolved bug](https://github.com/firebase/firebase-ios-sdk/issues/233) related to parsing `deepLink` for new app installs. In order to get it work your dynamic link MUST have an [app preview page](https://firebase.google.com/docs/dynamic-links/link-previews), which by default.

## Methods

### onDynamicLink(_callback_)
Registers callback that is triggered on each dynamic link click.
```js
cordova.plugins.firebase.dynamiclinks.onDynamicLink(function(data) {
    console.log("Dynamic link click with data: ", data);
});
```

[npm-url]: https://www.npmjs.com/package/cordova-plugin-firebase-dynamiclinks
[npm-version]: https://img.shields.io/npm/v/cordova-plugin-firebase-dynamiclinks.svg
[npm-downloads]: https://img.shields.io/npm/dm/cordova-plugin-firebase-dynamiclinks.svg

