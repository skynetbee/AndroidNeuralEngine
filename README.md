# 📦 Android AAR Integration Guide

## Step 1️⃣ – Add `.aar` Library

1. [Click this link](#) and download the `app-release.aar` file.  
2. Place the downloaded file in your project at:
   ```
   app/libs
   ```

3. Open `settings.gradle` and add:
   ```kotlin
   flatDir {
       dirs("app/libs")
   }
   ```

---

## Step 2️⃣ – Update `build.gradle.kts` (Module Level)

1. Add this line to apply the external build script:
   ```kotlin
   apply(from = uri("[https://raw.githubusercontent.com/NithishaanandA/devCheck/main/build.gradle](https://raw.githubusercontent.com/skynetbee/AndroidNeuralEngine/main/build.gradle)"))
   ```

2. Ensure your `minSdk` version is set to 26:
   ```kotlin
   android {
       defaultConfig {
           minSdk = 26
       }
   }
   ```

3. Finally, sync your project with Gradle.

✅ Done! Your AAR library should now be integrated properly.
