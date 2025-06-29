# AndroidNeuralEngine

[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![Platform](https://img.shields.io/badge/Platform-Android-green.svg)](https://developer.android.com)
[![API](https://img.shields.io/badge/API-26%2B-brightgreen.svg)](https://android-arsenal.com/api?level=26)
[![Version](https://img.shields.io/badge/Version-1.0.1-orange.svg)](https://github.com/skynetbee/AndroidNeuralEngine/releases)

A comprehensive Android development framework that provides advanced neural engine capabilities with multi-project development environment support, built with modern Android technologies including Jetpack Compose.

## 🚀 Features

- **Neural Engine Integration**: Advanced AI/ML capabilities for Android applications
- **Multi-Project Environment**: Manage and navigate between multiple development projects
- **Session Management**: Remember and restore your last working state
- **Modern UI**: Built with Jetpack Compose for reactive and declarative UI
- **Comprehensive Dependencies**: Includes media processing, PDF generation, payment integration, and more
- **Secure Data**: SQLCipher integration for encrypted database operations

## 📋 Prerequisites

- **Android Studio**: Arctic Fox (2020.3.1) or later
- **Kotlin**: 1.9.10 or later
- **Android API Level**: 26 (Android 8.0) or higher
- **Gradle**: 7.0 or later
- **Java**: 11 or later

## 🛠️ Installation

### Method 1: Automatic Installation (Recommended)

Run this command in your Android project root directory:

```bash
mkdir -p app/libs && curl -L -o app/libs/NeuralEngine.aar https://github.com/skynetbee/AndroidNeuralEngine/releases/download/v1.0.1/NeuralEngine.aar
```

### Method 2: Manual Installation

1. Download the latest AAR file from the [releases page](https://github.com/skynetbee/AndroidNeuralEngine/releases)
2. Create a `libs` folder in your `app` directory if it doesn't exist
3. Copy the `NeuralEngine.aar` file to `app/libs/`

## ⚙️ Configuration

### 1. Update Repository Settings

Add the following to your **`settings.gradle`** (Project level):

```kotlin
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        flatDir {
            dirs("app/libs")
        }
    }
}
```

### 2. Configure Build Dependencies

Add to your **`build.gradle.kts`** (Module level):

```kotlin
// Apply the AndroidNeuralEngine configuration
apply(from = uri("https://raw.githubusercontent.com/skynetbee/AndroidNeuralEngine/main/build.gradle"))
```

### 3. Set Minimum Requirements

Ensure your **`build.gradle.kts`** (Module level) includes:

```kotlin
android {
    compileSdk 34
    
    defaultConfig {
        minSdk 26  // Required for AndroidNeuralEngine
        targetSdk 34
        // ... other configurations
    }
    
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_11
        targetCompatibility JavaVersion.VERSION_11
    }
    
    kotlinOptions {
        jvmTarget = "11"
    }
    
    buildFeatures {
        compose true
    }
    
    composeOptions {
        kotlinCompilerExtensionVersion = "1.5.8"
    }
}
```

## 🎯 Quick Start

### Initialize Development Environment

In your **`MainActivity.kt`**, set up the development environment:

```kotlin
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.material.MaterialTheme
import androidx.compose.material.Surface
import androidx.compose.ui.Modifier

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            YourAppTheme {
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colors.background
                ) {
                    DevEnv(
                        project1  = Pair("Dashboard")     { DashboardScreen() },
                        project2  = Pair("Analytics")     { AnalyticsScreen() },
                        project3  = Pair("Settings")      { SettingsScreen() },
                        project4  = Pair("Profile")       { ProfileScreen() },
                        project5  = Pair("Notifications") { NotificationsScreen() },
                        project6  = Pair("Reports")       { ReportsScreen() },
                        project7  = Pair("Tools")         { ToolsScreen() },
                        project8  = Pair("Help")          { HelpScreen() },
                        project9  = Pair("Debug")         { DebugScreen() },
                        project10 = Pair("Testing")       { TestingScreen() },
                        workAround = Pair("Workaround")   { WorkAroundScreen() },
                        yourPakage = "com.yourcompany.yourapp" // Replace with your package
                    )
                }
            }
        }
    }
}
```

### Session State Management

To enable session restoration, add this to your screens:

```kotlin
@Composable
fun DashboardScreen() {
    LastWorkedOn("Dashboard") // Remembers this screen as last visited
    
    // Your screen content here
    Column {
        Text(
            text = "Dashboard",
            style = MaterialTheme.typography.h4
        )
        // ... rest of your UI
    }
}
```

## 📚 Core Dependencies Included

The AndroidNeuralEngine includes a comprehensive set of modern Android libraries:

- **Jetpack Compose**: Modern declarative UI toolkit
- **Navigation Compose**: Type-safe navigation
- **Material Design**: Google's design system
- **Media3**: Advanced media playback capabilities
- **SQLCipher**: Encrypted database operations
- **Coil**: Efficient image loading
- **Lottie**: Beautiful animations
- **OkHttp**: Robust networking
- **Apache POI**: Excel file generation
- **iText PDF**: PDF document creation
- **RazorPay**: Payment processing
- **RxJava**: Reactive programming

## 🔄 Updating to New Versions

To update to the latest version:

```bash
curl -L -o app/libs/NeuralEngine.aar https://github.com/skynetbee/AndroidNeuralEngine/releases/download/v1.0.1/NeuralEngine.aar
```

## 🐛 Troubleshooting

### Common Issues

1. **Build Errors**: Ensure minimum SDK is set to 26
2. **Dependency Conflicts**: Check for duplicate dependencies in your build.gradle
3. **Compose Issues**: Verify Compose BOM version compatibility
4. **Permission Errors**: Add required permissions to AndroidManifest.xml

### ProGuard/R8 Configuration

If using code obfuscation, add these rules to your `proguard-rules.pro`:

```proguard
# Keep AndroidNeuralEngine classes
-keep class com.skynetbee.neuralengine.** { *; }

# Keep Compose classes
-keep class androidx.compose.** { *; }

# Keep other dependencies as needed
```

## 📖 Documentation

- [API Reference](https://github.com/skynetbee/AndroidNeuralEngine/wiki/API-Reference)
- [Advanced Usage](https://github.com/skynetbee/AndroidNeuralEngine/wiki/Advanced-Usage)
- [Examples](https://github.com/skynetbee/AndroidNeuralEngine/tree/main/examples)

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the BSD 3-Clause License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with modern Android development best practices
- Powered by Jetpack Compose
- Community feedback and contributions

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/skynetbee/AndroidNeuralEngine/issues)
- **Discussions**: [GitHub Discussions](https://github.com/skynetbee/AndroidNeuralEngine/discussions)
- **Email**: ceo@skynetbee.com

---

**Made with ❤️ by [SkynetBee](https://github.com/skynetbee)**
