# [Unqualified Beta] LiveEngage In-App Messaging iOS SDK - Supported for XCode 9, Swift 4.0 and iOS11
**For beta usage only. Do not use for productive usage.
This version did not enter any testing or quality assurance cycles. Certified version is planned with v2.8**

This read.me include the quick start guide for LiveEngage In-App Messaging iOS SDK in Swift and Objective-C.


## SDK Documentation
Integration guide, API Documentation and Configurations can be found in Livepersons Developers Portal:
https://developers.liveperson.com/consumer-experience-ios-sdk-quick-start.html

## Installation
LiveEngage In-App Messaging SDK for iOS supports multiple methods of installations.

### Installation using CocoaPods
The SDK is also compatible with CocoaPods, a dependency manager for Swift and Objective-C Cocoa projects. CocoaPods has thousands of libraries and is used in over 2 million apps. It can help you scale your projects elegantly and provides a standard format for managing external libraries.

 1. Install cocoapods using the following command:
```
	$ gem install cocoapods
```
 2. Navigate to your project folder and init new pod using the following command:
```
	$ pod init
```
 3. Podfile should be created under your project’s folder.
 To integrate Liveperson Messaging SDK into your Xcode project using CocoaPods, specify it in your Podfile:
```
	source 'https://github.com/LivePersonInc/iOSPodSpecs.git'
	platform :ios, '8.0'
	use_frameworks!

	target '<Your Target Name>' do
	    pod 'LPMessagingSDK'
	end
```

 4. Run the following command in the terminal under your project folder:
```
	$ pod install
```
 5. Incase you wish to upgrade to the latest SDK version and you have already ran 'pod install', Run the following command:
```
 $ pod update
```

### Installation using Libraries Copy to Xcode Project
Copy all framework and bundle files into the project, including the bundle file In project settings, navigate to the General tab, and add all Framework files to the Embedded Binaries section.

### Installation notes

In project settings, navigate to the Build Phases tab, and click the + button to add a New Run Script Phase. Add the script below in order to loop through the frameworks embedded in the application and remove unused architectures (used for simulator). This step is a workaround for known iOS issue http://www.openradar.me/radar?id=6409498411401216 and is necessary for archiving your app before publishing it to the App Store.

If frameworks installed using CocoaPods, use the following script:
```
bash "${SRCROOT}/Pods/LPMessagingSDK/LPMessagingSDK/LPInfra.framework/frameworks-strip.sh"
```

If frameworks installed using copy to Xcode project, use the following script:
```
bash "${BUILT_PRODUCTS_DIR}/${FRAMEWORKS_FOLDER_PATH}/LPInfra.framework/frameworks-strip.sh"
```

## License
LIVEPERSON DEVELOPER LICENSE FOR SDK

By installing, accessing, downloading, or otherwise using the LP Messaging software development kit (“SDK”) and any related software code provided by LivePerson on Github’s website, you and your company, in consideration of the mutual agreements contained herein and intending to be legally bound hereby accept the terms of this developer license agreement (“License Agreement”) and agree to be bound the License Agreement.

License.
LivePerson grants you and your company a limited, revocable, non-exclusive, non-transferable, non-sublicensable license to access and use the SDK solely for testing, development and non-production use only.  You may not sell, sublicense, rent, loan or lease any portion of the SDK to any third party and you may not reverse engineer, decompile or disassemble any portion of the SDK. Prior to your and your company’s use of the SDK for commercial purposes, including in a production environment, you and your company must notify LivePerson and mutually agree in writing on the applicable pricing and license terms for such usage.

Term.
This License Agreement is effective until terminated. LivePerson has the right to terminate this agreement immediately if you fail to comply with any term herein. Upon any such termination, you and your company must remove all full and partial copies of the SDK from your computer, network, and servers and discontinue use of the SDK.

Proprietary Rights.
LivePerson retains all proprietary rights in and to the SDK, including know how, technologies, and trade secrets, and all derivative works, and enhancements and modifications to the foregoing. Except as stated in the above license, this License Agreement does not grant you and/or your company any rights to patents, copyrights, trade secrets, trademarks, or other rights with respect to the SDK.

Disclaimer of Warranty.
With respect to your and your company’s testing, development, and non-production use of the SDK, LivePerson provides the SDK “as is.”  To the maximum extent permissible under applicable law, LivePerson expressly disclaims all representations and warranties, whether express or implied warranties, concerning or related to the SDK, including but not limited to the implied warranties of non-infringement and/or fitness for a particular purpose.  LivePerson does not warrant, guarantee, or make any representations regarding the use, the results of the use or the benefits, of the SDK. Your commercial and production use of the SDK will be governed the mutually agreed upon commercial agreement in writing with LivePerson.
