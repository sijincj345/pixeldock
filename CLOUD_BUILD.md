# Cloud build — no Flutter installation required

This project includes GitHub Actions workflows that build the Android application in the cloud. You do **not** need Flutter, Android Studio, Java, or the Android SDK on your phone or computer.

## 1. Create a GitHub repository

Create a repository on GitHub, preferably **Private**, for the project.

## 2. Upload this project's files

Upload the contents of this folder to the repository. The `.github/workflows/` folder must also be uploaded.

Repository root should contain:

- `pubspec.yaml`
- `lib/`
- `assets/`
- `android/`
- `.github/workflows/build-apk.yml`
- `.github/workflows/build-aab.yml`

## 3. Build the installable APK

On GitHub open:

**Actions → Build offline Android APK → Run workflow**

Wait for the workflow to finish.

Open the completed workflow run and scroll to **Artifacts**. Download:

`csi-south-kerala-songbook-apk`

Inside it is:

`app-release.apk`

Copy that APK to your Android phone and install it. The songbook database is bundled inside the application, so the songs can be read without internet access.

## 4. Play Store AAB

For Google Play publishing:

**Actions → Build Play Store App Bundle → Run workflow**

Download the artifact:

`csi-south-kerala-songbook-aab`

This contains `app-release.aab`.

### Important signing note

The APK workflow creates a temporary CI signing key so the APK is installable for testing. That key is **not** the same as a permanent Play Store upload key. For a production Play Store release, create your own upload keystore and store its credentials in GitHub Actions secrets. Do not commit a private keystore or passwords to the repository.

## 5. Offline behavior

The application includes:

- 550 songs in `assets/data/songbook.db`
- 44 worship orders
- No network service is required to read the local songbook

Internet is only needed for downloading the APK, updating the application, or using external Android services such as sharing.

## 6. If you only have an Android phone

You can still do this through Chrome:

1. Open GitHub.
2. Create the repository.
3. Upload the project files.
4. Open **Actions**.
5. Select **Build offline Android APK**.
6. Tap **Run workflow**.
7. Download the artifact when the build finishes.
8. Install the APK on the phone.

You do not need to install Flutter.
