# 🚀 React Native Setup Guide - Windows 11 

## 📋 Table of Contents
- [Prerequisites](#-prerequisites)
- [Environment Setup](#-environment-setup)
- [Project Creation](#-project-creation)
- [Running Your App](#-running-your-app)
- [Common Issues](#-common-issues)
- [Useful Commands](#-useful-commands)
- [Learning Resources](#-learning-resources)

## 💻 Prerequisites
Before we dive in, make sure you have:
- Windows 11 OS
- A stable internet connection
- At least 8GB RAM (16GB recommended)
- 30GB+ free disk space

## 🛠 Environment Setup

### 1. Install Node.js 📦
```bash
# Visit https://nodejs.org
# Download & install LTS version
# Verify installation:
node --version
npm --version
```

### 2. Install Git 🌿
```bash
# Visit https://git-scm.com/downloads
# Download & install Git for Windows
# Verify installation:
git --version
```

### 3. Install VSCode 📝
- Download from https://code.visualstudio.com
- Install these awesome extensions: 
  - ⚛️ React Native Tools
  - 🎨 Prettier
  - ⚡ ESLint
  - 🏷️ Auto Close Tag
  - 🔄 Auto Rename Tag

### 4. Install Android Studio 🤖
```bash
# 1. Download from https://developer.android.com/studio
# 2. During installation, select:
#    - Android SDK
#    - Android SDK Platform
#    - Android Virtual Device
```

### 5. Set Environment Variables 🔧
```bash
# Open Windows Settings → System → About → Advanced system settings
# Click "Environment Variables"
# Add to User variables:
ANDROID_HOME = C:\Users\YourUsername\AppData\Local\Android\Sdk

# Add to Path:
%ANDROID_HOME%\platform-tools
%ANDROID_HOME%\tools
%ANDROID_HOME%\tools\bin
```

### 6. Install Expo CLI 📱
```bash
npm install -g expo-cli
```

## 🎯 Project Creation

### 1. Create New Project
```bash
# Replace MyAwesomeApp with your project name
npx create-expo-app MyAwesomeApp
cd MyAwesomeApp
```

### 2. Open in VSCode
```bash
code .
```

### 3. Add VSCode Settings ⚙️
Create `.vscode/settings.json`:
```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.tabSize": 2,
  "files.insertFinalNewline": true
}
```

## 🏃‍♂️ Running Your App

### 1. Start Development Server
```bash
npx expo start
```

### 2. Test on Real Device 📱
- Install "Expo Go" from Play Store/App Store
- Scan QR code with:
  - 🤖 Android: Expo Go app
  - 🍎 iOS: Phone camera

### 3. Test on Emulator 🖥️
```bash
# Start Android emulator first
npx expo start --android
```

## 🔧 Common Issues

### Metro Bundler Issues 🚇
```bash
# Clear cache
npx expo start -c

# Nuclear option: Delete node_modules
rm -rf node_modules
npm install
```

### Android Device Not Connecting 📵
1. ✅ Enable USB debugging
2. 🔌 Try different USB ports
3. 🔄 Restart ADB:
```bash
adb kill-server
adb start-server
```

### Expo Go Not Scanning QR 📷
1. 📡 Ensure phone & PC on same network
2. 🔄 Try switching connection type:
```bash
# Press 'd' in terminal for developer menu
# Press 'w' to toggle connection type
```

## 📝 Useful Commands

```bash
# Start project
npx expo start

# Clear cache & start
npx expo start -c

# Install packages
npm install package-name

# Run on Android
npx expo start --android

# Run on iOS (requires macOS)
npx expo start --ios

# Build standalone app
eas build
```

## 📚 Learning Resources

### Official Documentation 📖
- 📱 [React Native Docs](https://reactnative.dev/docs/getting-started)
- 🚀 [Expo Docs](https://docs.expo.dev)

### Community 👥
- 💬 [React Native Discord](https://discord.gg/react-native)
- 🤝 [Expo Forums](https://forums.expo.dev)
- ❓ [Stack Overflow](https://stackoverflow.com/questions/tagged/react-native)

### File Structure 📂
```
MyAwesomeApp/
├── 📱 App.js           # Main component
├── 🖼️ assets/          # Static files
├── 📦 package.json     # Dependencies
├── 📁 node_modules/    # Packages
├── 📝 .gitignore      # Git ignore
└── ⚙️ app.json        # Expo config
```

## 🎉 Success!
If you've followed all steps, you should now have a working React Native development environment! Happy coding! 🎨 👨‍💻 👩‍💻

## ⭐ Pro Tips
1. 💡 Use `console.log()` for debugging
2. 🔄 Enable Hot Reloading
3. 📱 Test on multiple devices
4. 🔍 Use React Native Debugger
5. ⚡ Keep dependencies updated

## 🆘 Need Help?
- Check the [troubleshooting guide](https://reactnative.dev/docs/troubleshooting)
- Search on [Stack Overflow](https://stackoverflow.com/questions/tagged/react-native)
- Ask in React Native Discord

---
Made with ❤️ by a fellow React Native developer
