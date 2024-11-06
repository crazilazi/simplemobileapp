# simplemobileapp
A simple mobile app using react native

# React Native Setup Using Chocolatey on Windows 11

## 1. Install Chocolatey
Open PowerShell as Administrator and run:
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

## 2. Install Dependencies
Run these commands in PowerShell (Administrator):

```powershell
# Install Node.js LTS, if it is not installed
choco install nodejs-lts -y

# Install OpenJDK 17, if it is not installed
choco install openjdk17 -y

# Install Android Studio, if it is not installed
choco install androidstudio -y

# Install Visual Studio Code, if it is not installed
choco install vscode -y

# Install Git (if needed), if it is not installed
choco install git -y

# Refresh environment variables
refreshenv
```

## 3. Android Studio Setup
1. Open Android Studio
2. Go to Settings/Preferences → Appearance & Behavior → System Settings → Android SDK
3. Select "SDK Platforms" tab and install:
   - Android 14.0 (API 34)
   - Android SDK Platform 34
   - Intel x86 Atom_64 System Image or Google APIs Intel x86 Atom System Image
   - Google Play Intel x86 Atom System Image (for Play Store testing)

4. Select "SDK Tools" tab and install:
   - Android SDK Build-Tools 34
   - Android SDK Command-line Tools
   - Android Emulator
   - Android SDK Platform-Tools

## 4. Create React Native APP
```powershell
npx @react-native-community/cli init SimpleMobileApp
```

## 5. Replace below in App.tsx

![image](https://github.com/user-attachments/assets/fbd1f09d-1237-4552-b5ab-035865f5debf)

```react
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
## 6. Run react native app in andriod emulator

```powershell
npm run android
```
## Optional. Set Environment Variables
Run in PowerShell (Administrator):

```powershell
# Set ANDROID_HOME
[System.Environment]::SetEnvironmentVariable('ANDROID_HOME', '$env:LOCALAPPDATA\Android\Sdk', 'User')

# Add platform-tools to Path
[System.Environment]::SetEnvironmentVariable('Path', $env:Path + ';$env:LOCALAPPDATA\Android\Sdk\platform-tools', 'User')

# Refresh environment
refreshenv
```
