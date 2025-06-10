# 🤖 AndroidNeuralEngine

**AndroidNeuralEngine** is a lightweight, high-performance `.aar` library designed for neural processing on Android devices. Built for modern Android apps, it helps developers integrate advanced neural capabilities with minimal effort.

## 🚀 Features

- Packaged as an `.aar` for easy integration
- Optimized for performance and minimal overhead
- Suitable for both Java and Kotlin projects
- Plug-and-play structure for fast setup

## 📦 Installation

### 🧠 Using the `.aar` Directly

1. Download the `app-release.aar` file from the [**Releases**](https://github.com/skynetbee/AndroidNeuralEngine/releases) section or the `libs/` directory.

2. In **Android Studio**:
   - Copy the `.aar` file to your project’s `libs/` folder.
   - Add the following to your `build.gradle` (app-level):

     ```groovy
     repositories {
         flatDir {
             dirs 'libs'
         }
     }

     dependencies {
         implementation(name: 'app-release', ext: 'aar')
     }
     ```

3. Sync the project and start building with NeuralEngine!

---

💡 Need help using the engine or contributing? Feel free to open an issue or reach out.  
Power your Android app with the strength of **NeuralEngine** ⚡
