# CSI South Kerala Songbook — Professional Flutter App

A polished offline Android songbook based on the supplied CSI South Kerala Diocese Songbook source.

## Included
- 550 songs
- 44 worship orders
- Offline SQLite database
- Material 3 professional UI
- Splash screen
- Home dashboard
- Search by number/title/lyrics
- Song index: A–Z and categories
- Favorites and recently opened songs
- Previous / Next navigation
- Immersive full-screen reading mode
- In-page Malayalam text-size control
- Share song text
- Light / dark / system theme
- Custom launcher icon

## Source note
The source PDF contains Malayalam embedded-font extraction artifacts. The database preserves the extracted source rather than silently changing its wording. For a production release, the song text should be proofread against the original pages or replaced with verified OCR/transcription.

## Build
Install Flutter, then from the project root run:

```bash
flutter pub get
flutter create .
flutter run
```

For release:

```bash
flutter build apk --release
```

The current development environment does not include the Flutter SDK, so an APK cannot be compiled or runtime-tested here.

## Cloud build (no Flutter installation)

See `CLOUD_BUILD.md`. GitHub Actions workflows are included under `.github/workflows/` for building an installable APK and a Play Store AAB in the cloud.
