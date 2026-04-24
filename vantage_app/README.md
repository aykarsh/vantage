# Vantage App

The mobile frontend for **Project Vantage**, an offline-first P2P payment system built with Flutter.

## 📱 Features

- **Offline Wallet**: Store and manage digital vouchers securely on-device.
- **P2P Transfer**: 
  - **Wi-Fi Aware (NAN)**: Discover and transfer vouchers to nearby peers without any internet or cellular connection.
  - **QR Transfers**: Scan and generate standard QR codes for visual handovers.
- **Secure Signing**: Ed25519 signatures used for every transaction to ensure integrity.
- **Background Sync**: Automatic settlement of transactions once the device detects an internet connection.

## 🔧 Technical Details

- **Language**: Dart / Flutter
- **Native Components**: 
  - `WifiAwareManager.kt`: Controls the Android NAN discovery.
  - `HardwareSigner.kt`: Integrates with Android Keystore.
- **Crypto Library**: [cryptography](https://pub.dev/packages/cryptography)

## 📁 Directory Structure

- `lib/core`: Models (`Voucher`, `Envelope`) and cryptographic logic.
- `lib/services`: Synchronization and connectivity management.
- `lib/ui`: Wallet dashboard and transaction screens.
- `android/`: Native implementations for hardware security and P2P discovery.

## 🚀 Running the App

```bash
# Get dependencies
flutter pub get

# Run build_runner (for json_serializable)
flutter pub run build_runner build

# Run on an attached device
flutter run
```

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
