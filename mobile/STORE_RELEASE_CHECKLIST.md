# My Finance Manager — Store Release Checklist

## Current status
- [x] Expo / React Native source is committed in `mobile/`.
- [x] Android package and iOS bundle identifiers are configured.
- [x] EAS build profiles are present.
- [ ] Dependencies and app must be validated on the current Expo SDK.
- [ ] Android and iOS test builds must be generated and tested.
- [ ] Store listing, privacy policy, screenshots, and support contact must be prepared.
- [ ] Developer accounts, signing, and store review must be completed by the app owner.

## 1. Before building
1. Create/sign in to an Expo account at https://expo.dev/.
2. From the `mobile` directory, install Node.js 22.13 or newer for the current Expo SDK, then run:
   ```sh
   npm install
   npx expo install --fix
   npx expo-doctor
   ```
3. Resolve every dependency or configuration error before requesting release builds.
4. Review the app identifiers in `app.json` before the first store release. Changing them later can complicate updates.
5. Add final app icon, adaptive Android icon, and splash assets before store builds.

## 2. Test Android APK
From `mobile/`:
```sh
npx eas-cli@latest login
npx eas-cli@latest build --platform android --profile preview
```
Install the generated APK on a real Android phone. Test adding, editing and reviewing records, language switching, dark mode, storage persistence, and app restart. Use test data only.

## 3. Build store binaries
After tests pass and accounts/credentials are ready:
```sh
npx eas-cli@latest build --platform all --profile production
```
The Android store artifact is normally an AAB; the iOS artifact is an IPA. A build is not the same as a published app.

## 4. Store accounts and release
- Google Play Console: developer account required; current Expo guidance lists a one-time US$25 registration fee.
- Apple Developer Program: paid membership required; current Expo guidance lists US$99/year.
- Create the app entries in Google Play Console and App Store Connect.
- Prepare app name, short/full descriptions, screenshots, support URL/email, age/content rating, privacy disclosures, and data-safety/privacy forms.
- Upload Android to an internal testing track first. Upload iOS to TestFlight first.
- Test on actual devices and fix issues before submitting for review.
- Store approval and public release are controlled by Google and Apple; they cannot be guaranteed.

## 5. Privacy and financial data
- This starter stores transaction records locally on the device and does not connect to bank accounts.
- Do not enter real financial information during initial testing.
- Before launch, add a published privacy policy and a support contact. Confirm that the policy accurately describes actual app behavior.
- Test data backup and recovery before relying on the app for important records. Do not commit transaction exports, credentials, API keys, signing files, or personal financial data to GitHub.
- The current starter is not a complete secure banking product. Review app lock/biometric protection, backup encryption, and data deletion behavior before public release.

## Official references
- Expo SDK versions: https://docs.expo.dev/versions/latest/
- EAS Build: https://docs.expo.dev/build/setup/
- Store submission: https://docs.expo.dev/deploy/submit-to-app-stores/
