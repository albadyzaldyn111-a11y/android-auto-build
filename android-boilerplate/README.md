# Android Auto Build Test App

A minimal, build-safe boilerplate with an automated CI/CD pipeline out of the box using **Kotlin**, **AndroidX AppCompat**, and **GitHub Actions**.

## Project Features
- **100% Build-Safe on Clean Environments**: Configured with strict repository modes and standard modern library constraints.
- **Fail-Proof Release Builder**: Uses `signingConfigs.debug` in release builds so that `./gradlew assembleRelease` works out-of-the-box on GitHub Actions without configuring premium keystore sign[...]
- **GitHub Action Pipeline Included**: Automatically runs tests and compiles release APKs on push or PRs.
- **Auto Release Publisher**: Automatically spins up a rich GitHub Release attaching the finalized standalone APK whenever you push a version tag matching `v*` (e.g. `git push origin v1.0.0`).

## Directory Layout
```
├── .github
│   └── workflows
│       └── build.yml
├── app
│   ├── build.gradle
│   └── src
│       └── main
│           ├── AndroidManifest.xml
│           ├── java/com/example/autobuild/MainActivity.kt
│           └── res/layout/activity_main.xml
├── gradle/wrapper/gradle-wrapper.properties
├── build.gradle
├── settings.gradle
└── README.md
```

## Getting Started
1. Push these files directly to a new repository on GitHub (make sure the structure matches the root of your repository).
2. To trigger a real release with APK downloads:
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```
3. Watch the compilation complete in the **Actions** tab of your repository. Your release will be instantly published with the downloadable APK!
