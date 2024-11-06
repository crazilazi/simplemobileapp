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
# Install Node.js LTS
choco install nodejs-lts -y

# Install OpenJDK 17
choco install openjdk17 -y

# Install Android Studio
choco install androidstudio -y

# Install Visual Studio Code
choco install vscode -y

# Install Git (if needed)
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

## 4. Set Environment Variables
Run in PowerShell (Administrator):

```powershell
# Set ANDROID_HOME
[System.Environment]::SetEnvironmentVariable('ANDROID_HOME', '$env:LOCALAPPDATA\Android\Sdk', 'User')

# Add platform-tools to Path
[System.Environment]::SetEnvironmentVariable('Path', $env:Path + ';$env:LOCALAPPDATA\Android\Sdk\platform-tools', 'User')

# Refresh environment
refreshenv
```

## 5. Create React Native APP
```powershell
npx @react-native-community/cli init SimpleMobileApp
```
