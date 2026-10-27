# My Finance Manager — Android + iOS

This folder contains the Expo / React Native app for Android and iOS, separate from the static web app at the repository root.

## Features in this starter
- AED balance, income, expenses and net savings dashboard
- Add income and expense transactions
- Transaction history with category and date
- Simple monthly budget overview
- English / Tamil labels
- Dark mode toggle
- Local device storage using AsyncStorage

## Run on a phone
1. Install Node.js 22.13 or newer.
2. From the repository root, run:
   ```sh
   cd mobile
   npm install
   npx expo install --fix
   npx expo-doctor
   npx expo start
   ```
3. Install Expo Go on your phone and scan the QR code. Both devices should be on a compatible network.
4. Resolve any dependency/configuration warnings before making a release build.

## Create an Android test APK
You need an Expo account. From `mobile/`:
```sh
npx eas-cli@latest login
npx eas-cli@latest build --platform android --profile preview
```
When the build finishes, open its build page and install the APK on an Android device.

## Build Android and iOS for store review
After validating the app and configuring developer accounts/signing:
```sh
npx eas-cli@latest build --platform all --profile production
```
This requests production builds; it does not automatically publish the app. Use Google Play Console and App Store Connect to complete listings, testing, and review. See [STORE_RELEASE_CHECKLIST.md](./STORE_RELEASE_CHECKLIST.md).

## Privacy
- Transaction records are stored locally on the device via AsyncStorage. This starter does not connect to a bank or send transaction data to a server.
- App data may be lost if the app is removed or device data is cleared. Test backup/export and recovery before relying on it for important records.
- Never commit real financial data, exports, credentials, signing files, or API keys to this repository.
- The Face ID usage description is configured for possible future biometric-lock work; this starter does not yet implement a Face ID / Android biometric gate.

## App identifiers
- iOS: `com.yaseeninoor.myfinancemanager`
- Android: `com.yaseeninoor.myfinancemanager`

Confirm the package and bundle identifiers before your first store release. Changing them after launch can complicate updates.
