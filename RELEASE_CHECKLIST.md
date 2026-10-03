# Play Store Release Checklist

- [ ] Confirm publisher/organization name.
- [ ] Confirm rights/permission to distribute the 550 songs and 44 worship-order materials.
- [ ] Confirm rights to use CSI names/logos and any third-party material.
- [ ] Add official support email.
- [ ] Host the privacy policy at a public HTTPS URL.
- [ ] Create Google Play Console developer account if needed.
- [ ] Create the app in Play Console.
- [ ] Use package ID: `com.csiskd.songbook`.
- [ ] Keep versionName/versionCode in sync for each release.
- [ ] Configure Play App Signing in Play Console.
- [ ] Create an upload keystore and keep it securely backed up.
- [ ] Run `flutter clean`.
- [ ] Run `flutter pub get`.
- [ ] Run `flutter analyze`.
- [ ] Run `flutter test`.
- [ ] Run `flutter build appbundle --release`.
- [ ] Test the AAB on an internal testing track.
- [ ] Verify Malayalam rendering on multiple Android devices.
- [ ] Verify search, favorites, sharing, theme, font size, and offline behavior.
- [ ] Prepare Play Store icon, feature graphic, phone screenshots, and localized listing text.
- [ ] Complete Play Console Data safety and content declarations based on the final implementation.
- [ ] Complete content rating questionnaire.
- [ ] Complete target audience information.
- [ ] Upload AAB to testing/production as appropriate.

## Important
Do not publish until content ownership/permission has been confirmed. This project contains songbook content supplied by the user; the source file alone does not establish publishing rights.
