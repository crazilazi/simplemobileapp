# 📱 SimpleMobileApp
A simple mobile app using React Native

## 📋 Table of Contents
- [Chocolatey Installation](#-chocolatey-installation)
- [Dependencies Setup](#-dependencies-setup)
- [Android Studio Configuration](#-android-studio-configuration)
- [Project Creation](#-project-creation)
- [Code Implementation](#-code-implementation)
- [Running the App](#-running-the-app)
- [Environment Setup](#-environment-setup-optional)

## 🍫 Chocolatey Installation

### Open PowerShell as Administrator 👨‍💻
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

## 📦 Dependencies Setup

Run these commands in PowerShell (Administrator):
```powershell
# Install essential development tools
choco install nodejs-lts -y     # ⚡ Node.js LTS
choco install openjdk17 -y      # ☕ Java Development Kit
choco install androidstudio -y  # 🤖 Android Studio
choco install vscode -y         # 📝 Visual Studio Code
choco install git -y           # 🌿 Git

# Refresh environment variables
refreshenv
```

### 2. Install SDK Components 📱
In "SDK Platforms" tab, install anroid 14 or 15 and their api's:
- ✅ Android 14.0 (API 34)
- ✅ Android SDK Platform 34
- ✅ Intel x86 Atom_64 System Image
- ✅ Google APIs Intel x86 Atom System Image

In "SDK Tools" tab, install:
- ✅ Android SDK Build-Tools 34
- ✅ Android SDK Command-line Tools
- ✅ Android Emulator
- ✅ Android SDK Platform-Tools

### 3. Create Android Virtual Device (AVD) 📱

## 🎯 Project Creation
```powershell
npx @react-native-community/cli init SimpleMobileApp
```

## 💻 Code Implementation

Replace the content in `App.tsx` with:

```typescript
import React, {useState} from 'react';
import {
  SafeAreaView,
  ScrollView,
  StatusBar,
  StyleSheet,
  Text,
  TouchableOpacity,
  View,
  useColorScheme,
} from 'react-native';

const App = () => {
  const [counter, setCounter] = useState(0);
  const isDarkMode = useColorScheme() === 'dark';

  const backgroundStyle = {
    backgroundColor: isDarkMode ? '#000000' : '#FFFFFF',
  };

  return (
    <SafeAreaView style={[styles.container, backgroundStyle]}>
      <StatusBar barStyle={isDarkMode ? 'light-content' : 'dark-content'} />
      <ScrollView contentInsetAdjustmentBehavior="automatic">
        <View style={styles.header}>
          <Text style={styles.title}>React Native Community CLI</Text>
          <Text style={styles.subtitle}>Android 14 Project</Text>
        </View>
        <View style={styles.mainContent}>
          <Text style={styles.counterText}>Counter: {counter}</Text>
          <View style={styles.buttonRow}>
            <TouchableOpacity
              style={styles.button}
              onPress={() => setCounter(c => c - 1)}>
              <Text style={styles.buttonText}>Decrease</Text>
            </TouchableOpacity>
            <TouchableOpacity
              style={styles.button}
              onPress={() => setCounter(c => c + 1)}>
              <Text style={styles.buttonText}>Increase</Text>
            </TouchableOpacity>
          </View>
        </View>
      </ScrollView>
    </SafeAreaView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
  },
  header: {
    padding: 20,
    alignItems: 'center',
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 8,
  },
  subtitle: {
    fontSize: 16,
    opacity: 0.7,
  },
  mainContent: {
    flex: 1,
    alignItems: 'center',
    padding: 20,
  },
  counterText: {
    fontSize: 48,
    fontWeight: 'bold',
    marginBottom: 32,
  },
  buttonRow: {
    flexDirection: 'row',
    gap: 16,
  },
  button: {
    backgroundColor: '#007AFF',
    paddingHorizontal: 24,
    paddingVertical: 12,
    borderRadius: 8,
    elevation: 3,
  },
  buttonText: {
    color: '#FFFFFF',
    fontSize: 16,
    fontWeight: '600',
  },
});

export default App;
```

## 🚀 Running the App
```powershell
npm run android
```

## ⚙️ Environment Setup (Optional)

Run in PowerShell (Administrator):
```powershell
# Set ANDROID_HOME 🏠
[System.Environment]::SetEnvironmentVariable('ANDROID_HOME', '$env:LOCALAPPDATA\Android\Sdk', 'User')

# Add platform-tools to Path 🛠
[System.Environment]::SetEnvironmentVariable('Path', $env:Path + ';$env:LOCALAPPDATA\Android\Sdk\platform-tools', 'User')

# Refresh environment 🔄
refreshenv
```

## 🎉 Features
- ⚡ Modern React Native setup
- 🌙 Dark/Light mode support
- 🔢 Interactive counter
- 📱 Responsive design
- 🎨 Clean UI/UX

## 🔧 Requirements
- Windows 11
- PowerShell (Administrator access)
- Internet connection

---
📱 Happy Coding! Made with ❤️ using React Native
