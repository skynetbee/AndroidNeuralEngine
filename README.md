# 📦 Android AAR Integration Guide

## 📦 Step 1 – Add `.aar` Automatically

Just run this command in your terminal (inside your Android project root):

```bash
mkdir -p app/libs && curl -L -o app/libs/NeuralEngine.aar https://github.com/skynetbee/AndroidNeuralEngine/releases/download/v1.0.1/NeuralEngine.aar
```

Edit **`settings.gradle`**:
   ```kotlin
   flatDir {
       dirs("app/libs")
   }
   ```

---

## Step 2️⃣ – Update **`build.gradle.kts`** (Module level)

```kotlin
// Apply external build script
apply(from = uri("https://raw.githubusercontent.com/skynetbee/AndroidNeuralEngine/main/build.gradle"))
```

## Requirements

```kotlin
android {
    defaultConfig {
        minSdk = 26          // 🚨 keep minSdk 26
    }
}
```

Sync Gradle and you’re good to go.

---

## Step 3️⃣ – Wire Up `DevEnv` in **`MainActivity.kt`**

```kotlin
DevEnv(
    project1  = Pair("Project1")  { Project()  },
    project2  = Pair("Project2")  { Project1() },
    project3  = Pair("Project3")  { Project2() },
    project4  = Pair("Project4")  { Project3() },
    project5  = Pair("Project5")  { Project4() },
    project6  = Pair("Project6")  { Project5() },
    project7  = Pair("Project7")  { Project6() },
    project8  = Pair("Project8")  { Project7() },
    project9  = Pair("Project9")  { Project8() },
    project10 = Pair("Project10") { Project9() },
    workAround = Pair("workaround") { WorkAround() },
    yourPakage = "com.example.yourAppPackage"   // ← replace with your real package
)
```

Each **Project1 – Project10** (plus **workaround**) represents a *route* pointing to the corresponding Composable or activity.

---

## Step 4️⃣ (optional but 🔥) – Remember Where You Left Off

Inside any project screen, sprinkle this helper so the dev environment remembers your last session:

```kotlin
@Composable
fun Project() {
    LastWorkedOn("Project")      // 🧠 bookmark last-visited screen
    Text(text = "Hello!")
}
```

---

🚀 That’s it! Your multi-project dev playground is now set up and tracking where you left off. Hack away!
