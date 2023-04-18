# Android-Project-Setup
Android Project Setup Information

## Setup for Windows OS

### Start

* Java: Download Suitable openJdk -> [here](https://jdk.java.net/archive/)

* Kotlin: Download Latest Kotlin Compiler -> [here](https://github.com/JetBrains/kotlin/releases)

* Setup Environment Variables:

    * System Variables -> Add `JAVA_HOME` -> path to openjdk folder

    * User Variables -> Add path to `kotlinc\bin` inside `path` variable

### Open `cmd`

> Check Java version:  `java -version`
```
C:\Users\PotterTheCoder>java -version
openjdk version "17.0.2" 2022-01-18
OpenJDK Runtime Environment (build 17.0.2+8-86)
OpenJDK 64-Bit Server VM (build 17.0.2+8-86, mixed mode, sharing)
```

> Locate Jdk: `where java`
```
C:\Users\PotterTheCoder>where java
C:\Downloads\jdk-17.0.2\bin\java.exe
```

> Check Kotlin version: `kotlin -version`
```
C:\Users\PotterTheCoder>kotlin -version
Kotlin version 1.8.20-release-327 (JRE 17.0.2+8-86)
```

### Creating project in Android Studio:

> About Android Studio
```
Android Studio Flamingo | 2022.2.1
Build #AI-222.4459.24.2221.9862592, built on March 31, 2023
Runtime version: 17.0.6+0-b2043.56-9586694 amd64
VM: OpenJDK 64-Bit Server VM by JetBrains s.r.o.
```

> Create new project with _**Empty Activity**_ template:

_**Name:**_  
_**Package Name:**_  
_**Project Location:**_  
_**Minimun SDK: 23**_  

> Project level `build.gradle` looks like this:
```
plugins {
    id 'com.android.application' version '8.0.0' apply false
    id 'com.android.library' version '8.0.0' apply false
    id 'org.jetbrains.kotlin.android' version '1.8.20' apply false
}
```

> Module/App level `build.gradle` looks like this:
```
plugins {
    id 'com.android.application'
    id 'org.jetbrains.kotlin.android'
}
android {
    namespace 'com.daily'
    compileSdk 33
    defaultConfig {
        applicationId "com.daily"
        minSdk 23
        targetSdk 33
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
        vectorDrawables {
            useSupportLibrary true
        }
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_17
        targetCompatibility JavaVersion.VERSION_17
    }
    kotlinOptions {
        jvmTarget = JavaVersion.VERSION_17.toString()
    }
    buildFeatures {
        compose true
    }
    composeOptions {
        kotlinCompilerExtensionVersion '1.4.5'
    }
    packagingOptions {
        resources {
            excludes += '/META-INF/{AL2.0,LGPL2.1}'
        }
    }
}
dependencies {
    implementation 'androidx.core:core-ktx:1.10.0'

    implementation 'androidx.activity:activity-compose:1.7.0'

    implementation 'androidx.lifecycle:lifecycle-runtime-ktx:2.6.1'

    implementation platform('androidx.compose:compose-bom:2023.04.00')
    implementation 'androidx.compose.ui:ui'
    implementation 'androidx.compose.ui:ui-graphics'
    implementation 'androidx.compose.ui:ui-tooling-preview'
    implementation 'androidx.compose.material3:material3'

    androidTestImplementation platform('androidx.compose:compose-bom:2023.04.00')
    androidTestImplementation 'androidx.compose.ui:ui-test-junit4'
    debugImplementation 'androidx.compose.ui:ui-tooling'
    debugImplementation 'androidx.compose.ui:ui-test-manifest'

    testImplementation 'junit:junit:4.13.2'
    androidTestImplementation 'androidx.test.ext:junit:1.1.5'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.5.1'
}
```
