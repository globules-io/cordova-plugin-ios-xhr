# cordova-plugin-ios-xhr
## cordova-ios 6+ File XHR Plugin

### ARCHIVED
This plugin is not needed anymore

### About
> Originally, this plugin was a merge of two other plugins, and made compatible for cordova-ios 6+.

> [cordova-plugin-wkwebview-file-xhr](https://github.com/oracle/cordova-plugin-wkwebview-file-xhr)

> [cordova-plugin-wkwebviewxhrfix](https://github.com/TheMattRay/cordova-plugin-wkwebviewxhrfix)

> It's been since remodified and the code from [TheMattRay](https://github.com/TheMattRay) has now been entirely removed. It is kept here as original reference. 
> This could be turned into a PR to [cordova-plugin-wkwebview-file-xhr](https://github.com/oracle/cordova-plugin-wkwebview-file-xhr), if time allows it, or if anybody wants to go at it! All credits go to Oracle. 

### Install

> Install latest release

     cordova plugin add @globules-io/cordova-plugin-ios-xhr
     
> Or install from github master

     cordova plugin add https://github.com/globules-io/cordova-plugin-ios-xhr
     
### Uninstall

     cordova plugin rm @globules-io/cordova-plugin-ios-xhr
     
### Preferences

     <preference name="NativeXHRLogging" value="full|none" />
     <preference name="AllowUntrustedCerts"  value="true|false" />
     <preference name="InterceptRemoteRequests" value="all|secureOnly|none" />
     <preference name="allowFileAccessFromFileURLs" value="true|false" />
     <preference name="allowUniversalAccessFromFileURLs" value="true|false" />
     
### Description

>The default behavior of WKWebView is to raise a cross origin exception when loading files from the main bundle using the file protocol - "file://". This plugin works around this shortcoming by loading files via native code if the web view's current location has "file" protocol and the target URL passed to the open method of the XMLHttpRequest is relative. As a security measure, the plugin verifies that the standardized path of the target URL is within the "www" folder of the application's main bundle or in the /Library path of the application data directory.

>Since the application's starting page is loaded from the device's file system, all XHR requests to remote endpoints are considered cross origin. For such requests, WKWebView specifies "null" as the value of the Origin header, which will be rejected by endpoints that are configured to disallow requests from the null origin. This plugin works around that issue by handling all remote requests at the native layer where the origin header will be excluded

>Fixes local file access via XHR with WKWebView

>CustomUserAgent is only set for XHR requests and does not override cordova's OverrideUserAgent
