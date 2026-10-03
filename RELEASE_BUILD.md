# Release build guide

This project is configured for Google Play's current Android target requirement for new apps: Android 16 / API 36.

Google Play requires new apps and updates submitted from 31 August 2026 to target API 36 or higher. See the official Play Console documentation before release.

## 1. Install prerequisites

Install the current stable Flutter SDK and Android Studio/Android SDK. Ensure Android SDK Platform 36 and a compatible JDK are installed.

Then:

```bash
flutter doctor
flutter pub get
flutter analyze
flutter test
```

## 2. Generate/refresh Flutter platform wrappers

If your Flutter SDK expects additional platform wrapper files, from the project root run:

```bash
flutter create .
```

After this command, verify that these release settings are still present:

- applicationId `com.csiskd.songbook`
- namespace `com.csiskd.songbook`
- targetSdk 36
- versionCode/versionName
- release minification settings

## 3. Configure signing

Create an upload keystore, for example:

```bash
keytool -genkeypair -v -keystore upload-keystore.jks -keyalg RSA -keysize 2048 -validity 10000 -alias upload
```

Copy `android/key.properties.example` to `android/key.properties` and fill in the values. Keep both the keystore and key.properties private.

For the final Play release, use Google Play App Signing. The AAB you upload should be signed with your upload key.

## 4. Build the Play Store bundle

```bash
flutter clean
flutter pub get
flutter build appbundle --release
```

Output:

`build/app/outputs/bundle/release/app-release.aab`

## 5. Test before production

Upload the AAB to an Internal testing track first. Verify:

- app installation/update
- Malayalam text rendering
- 550-song database access
- 44 worship-order entries
- search/index
- favorites and recents
- sharing
- dark/light theme
- font size
- offline operation
- Android back navigation

## 6. Play Console declarations

Complete the Data safety, content rating, target audience, app access, and other Play Console declarations according to the final app behavior and publisher information. Do not guess these declarations; answer them from the actual final build.
