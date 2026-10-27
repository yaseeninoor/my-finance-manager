# My Finance Manager — Android + iOS

This folder contains the Expo / React Native app. It is a native mobile project for Android and iOS, separate from the static web app at the repository root.

## Features in this starter
- AED balance, income, expenses and net savings dashboard
- Add income and expense transactions
- Transaction history with category and date
- Simple monthly budget overview
- English / Tamil labels
- Dark mode toggle
- Local device storage using AsyncStorage

## Run on a phone
1. Install Node.js 20.19.4 or newer on a computer.
2. Open a terminal and run:
   ```sh
   cd mobile
   npm install
   npx expo start
   ```
3. Install **Expo Go** on your phone, then scan the QR code. Both devices should be on a compatible network.
4. For simulator/device builds, use the Expo CLI's Android/iOS options. iOS simulator builds require macOS and Xcode.

## Build installable apps
For production builds, configure an Expo account and EAS Build, then run:
```sh
npm install -g eas-cli
eas login
eas build:configure
eas build --platform android
eas build --platform ios
```
Publishing to Google Play or the Apple App Store requires the relevant developer account, app-store metadata, privacy disclosures and testing. A successful source-code commit does not itself create or publish an APK/IPA.

## Privacy
- Transaction records are stored locally on the device via AsyncStorage; this starter does not connect to a bank or send transaction data to a server.
- App data may be lost if the app is removed or device data is cleared. Add and test encrypted backup/export before relying on it for important records.
- Never commit real personal financial data or backups into this repository.
- Face ID usage description is configured for future biometric-lock work; this starter does not yet implement a Face ID / Android biometric gate.

## App identifiers
- iOS: `com.yaseeninoor.myfinancemanager`
- Android: `com.yaseeninoor.myfinancemanager`

If you later publish under a different developer account or brand, confirm the package and bundle identifiers before your first store release.