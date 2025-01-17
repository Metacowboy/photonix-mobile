# Photonix Mobile App

This is the code for generating React Native apps for Android and iOS devices. We use [Expo](https://expo.io/) to make it easier to develop and make builds.

## METANOTE 
 - this Project supports Expo SDK 40.0.0   - aktual is SDK 44.0.0 Client suports down to 41
 - Update package or Use older Expo client

Clone the repo if you haven't already and change into the project directory.

    git clone git@github.com:damianmoore/photonix-mobile.git
    cd photonix-mobile

You'll need to install the Expo CLI and NPM packages. If you have Yarn installed on your system run the following.

    yarn global add expo-cli
    yarn

The quickest way to run the app in a development environment is to download the [Expo client](https://expo.io/tools#client) on your device. You can then run the follow command and a QR code will then be shown which you can scan with Expo Client on your device.

    yarn start

If you have virtual devices/simulators for Android or iOS on your computer, you can run once of the following to launch on those.

    yarn android
    yarn ios

## Publishing

Before building a new version for Android or iOS, increment the version number `expo.version` in `app.json`.

### Google Play

Increment `expo.android.versionCode` in `app.json`.

    expo build:android -t app-bundle

Go to Expo page URL shown in the terminal to download `.aab` file when built.

### Apple App Store

Increment `expo.ios.buildNumber` in `app.json`.

    expo build:ios

Go to Expo page URL shown in the terminal to download `.ipa` file when built.

From an Apple computer with Xcode installed, upload to App Store Connect with the following command. You will need to use the app-specific password, not your usual Apple ID password.

    xcrun altool --upload-app --type ios --file path/to/application.ipa --username APPLE_ID --password APP_SPECIFIC_PASSWORD

Go to App Store Connect, select the app, then the Testflight tab. You should see the uploaded version listed. There will be a period of processing and then the app should be testable for any users listed in the Internal Group who have TestFlight installed.

#### Simulator devices needed for screenshots

- iPhone 6.5" Display - Not sure, iPhone 12 was closest found
- iPhone 5.5" Display - iPhone 8 Plus
- iPad Pro (both) - iPad Pro 12.9 inch

## What's in the app?

## TODO 
- Scrolling without image click 
- Multiseleect 

This app should be considered a client which is connected to an installation of [Photonix Server](https://github.com/damianmoore/photonix). Without an internet connection to a server, the app is currently next to useless. The main reason for creating this app was to give people quick access to their photo libraries from their phone or mobile device. Next, we intend to offer the option of detecting new photos when they are taken on the device and automatically uploading.
