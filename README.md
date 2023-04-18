# Android-Project-Setup
Android Project Setup Information

## Setup for Windows OS

Java: Download Suitable openJdk -> [here](https://jdk.java.net/archive/)

Kotlin: Download Latest Kotlin Compiler -> [here](https://github.com/JetBrains/kotlin/releases)

Setup Environment Variables:

System Variables -> Add `JAVA_HOME` -> path to openjdk folder

User Variables -> Add path to `kotlinc\bin` inside `path` variable

Open `cmd`

Check Java version:  `java -version`
```
C:\Users\PotterTheCoder>java -version
openjdk version "17.0.2" 2022-01-18
OpenJDK Runtime Environment (build 17.0.2+8-86)
OpenJDK 64-Bit Server VM (build 17.0.2+8-86, mixed mode, sharing)
```

Locate Jdk: `where java`
```
C:\Users\PotterTheCoder>where java
C:\Downloads\jdk-17.0.2\bin\java.exe
```

Check Kotlin version: `kotlin -version`
```
C:\Users\PotterTheCoder>kotlin -version
Kotlin version 1.8.20-release-327 (JRE 17.0.2+8-86)
```
