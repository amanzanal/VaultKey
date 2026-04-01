<div align="center">

# 🔐 VaultKey

### Local password manager for Android & iOS

**No account. No internet. No compromises.**

Built with Flutter · AES-256 encrypted · 100% offline

---

![Flutter](https://img.shields.io/badge/Flutter-3.16+-02569B?style=flat&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-3.0+-0175C2?style=flat&logo=dart&logoColor=white)
![Android](https://img.shields.io/badge/Android-5.0+-3DDC84?style=flat&logo=android&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-12+-000000?style=flat&logo=apple&logoColor=white)
![License](https://img.shields.io/badge/License-Proprietary-red?style=flat)

</div>

---

## What is VaultKey?

VaultKey is a **fully local** password manager. Your passwords never leave your device — no cloud sync, no login, no tracking. Everything is encrypted with AES-256 and protected by a PIN or custom password of your choice.

---

## ✨ Features

| | Feature | Description |
|---|---|---|
| 🔒 | PIN or password lock | Protect access with a 6-digit PIN or a custom password |
| 🔐 | AES-256 encryption | All entries encrypted locally using AES-256-CBC |
| 🗂️ | Categories | 8 categories to keep your vault organized |
| ⭐ | Favorites | Pin important entries to the top |
| 🔍 | Search & filter | Real-time filtering by title, username or website |
| 🎲 | Password generator | Generate strong passwords from 8 to 32 characters |
| 💪 | Strength indicator | Animated 5-level strength bar |
| 📋 | One-tap copy | Copy username or password instantly |
| 📤 | Backup export | Export your vault and share it via email or any app |

---

## 📱 Screens

| Lock screen | Vault | Entry detail | Settings |
|---|---|---|---|
| PIN or password unlock | Search, filter by category | Copy fields with one tap | Backup & security |

---

## 🚀 Getting started

### Requirements

- Flutter 3.16+
- Dart 3.0+
- Android 5.0+ (API 21) or iOS 12+

### Run locally

```bash
git clone https://github.com/your-username/vaultkey.git
cd vaultkey
flutter pub get
flutter run
```

### Build APK

```bash
flutter build apk --release
```

Output: `build/app/outputs/flutter-apk/app-release.apk`

### Build IPA (iOS)

```bash
flutter build ios --release
```

---

## 🔒 Security

- Master encryption key stored in **Keychain (iOS)** or **Keystore (Android)** via `flutter_secure_storage`
- **AES-256-CBC** with a random IV generated per write operation
- `android:allowBackup="false"` prevents Android from copying sensitive data
- Zero telemetry — no network calls whatsoever

> ⚠️ The exported backup file is **not encrypted**. Store it in a safe place and never share it publicly.

---

## 🗂️ Project structure

```
lib/
├── main.dart
├── theme/
│   └── app_theme.dart                 # Global colors and styles
├── models/
│   └── password_entry.dart            # Entry model
├── services/
│   ├── storage_service.dart           # Encrypted local storage
│   ├── encryption_service.dart        # AES-256 + password generator
│   └── backup_service.dart            # JSON export
├── screens/
│   ├── pin_setup_screen.dart          # Create / confirm / unlock
│   ├── home_screen.dart               # Main vault list
│   ├── add_edit_password_screen.dart  # Create and edit entries
│   ├── password_detail_screen.dart    # View details and copy
│   └── settings_screen.dart          # Backup and settings
└── widgets/
    └── password_strength_bar.dart     # Animated strength bar
```

---

## 📦 Dependencies

| Package | Purpose |
|---|---|
| `flutter_secure_storage` | OS-level encrypted storage |
| `encrypt` | AES-256 encryption |
| `uuid` | Unique entry IDs |
| `share_plus` | Backup file sharing |
| `path_provider` | Device folder access |
| `shared_preferences` | Non-sensitive preferences |

---

## 🛠️ Customization

### Add categories
Edit `lib/models/password_entry.dart`:
```dart
static const List<String> categories = [
  'General', 'Social Media', ... // Add here
];

static const Map<String, String> categoryIcons = {
  'My category': '🎯', // And here
};
```

### Change theme colors
Edit `lib/theme/app_theme.dart`:
```dart
static const Color accent = Color(0xFF4F8EF7);      // Primary color
static const Color background = Color(0xFF0A0E1A);  // Background
```

---

## License

Copyright (c) 2026 Almudena. All rights reserved.

This source code is publicly visible for educational and portfolio purposes only.
Unauthorized copying, modification, distribution, sublicensing, or commercial use
of this software, in whole or in part, is strictly prohibited without the express
written permission of the copyright owner.
