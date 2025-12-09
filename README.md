# PPFO Android v24.0

نسخة أندرويد من أداة PPFO للحسابات الرياضية المتقدمة (تحليل العوامل، أعداد ميرسين، زيتا، تايلور).

## How to Build

### Prerequisites
- JDK 17
- Android SDK

### Build on Google Colab

To build this APK directly inside a Google Colab notebook, follow these steps:

1. **Create a new Notebook**.
2. **Install Dependencies** (JDK 17 & Android Command Line Tools):
   ```bash
   !sudo apt-get update
   !sudo apt-get install -y openjdk-17-jdk
   !wget https://dl.google.com/android/repository/commandlinetools-linux-9477386_latest.zip
   !unzip commandlinetools-linux-9477386_latest.zip
   !mkdir -p android-sdk/cmdline-tools
   !mv cmdline-tools android-sdk/cmdline-tools/latest
   !yes | android-sdk/cmdline-tools/latest/bin/sdkmanager --licenses
   ```
3. **Set Environment Variables**:
   ```python
   import os
   os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-17-openjdk-amd64"
   os.environ["ANDROID_HOME"] = "/content/android-sdk"
   ```
4. **Clone/Create Project Files**:
   (Copy the files provided in this JSON to the Colab file system).
5. **Build**:
   ```bash
   !chmod +x gradlew
   !./gradlew assembleDebug
   ```
6. **Download APK**:
   The APK will be located at `app/build/outputs/apk/debug/app-debug.apk`.

### Local Build
1. Open project in Android Studio.
2. Sync Gradle.
3. Run on Emulator/Device.