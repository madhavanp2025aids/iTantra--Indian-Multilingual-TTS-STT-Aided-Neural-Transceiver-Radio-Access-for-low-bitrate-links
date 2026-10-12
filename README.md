# iTantra

**Indian Multilingual TTS-STT Aided Neural Transceiver Radio Access for Low-Bitrate Links**

---

## 📌 Overview

**iTantra** is an Android application designed for resilient, offline, and peer-to-peer communication over bandwidth-constrained and infrastructure-less environments. Utilizing compact **Protocol Buffers** serialization, **Google Nearby Connections / Wi-Fi Direct**, on-device **Vosk Speech-to-Text (STT)**, **ML Kit Translation**, and **Text-to-Speech (TTS)**, iTantra enables seamless cross-lingual voice and text messaging without requiring active internet connectivity or cellular networks.

---

## 🚀 Key Features

- **🌐 Offline Mesh & P2P Connectivity**:
  - Direct device discovery and communication using Google Nearby Connections API and Wi-Fi Direct.
  - Zero internet dependence for core chat, discovery, and handshake.

- **🗣️ Indian Multilingual Speech & Translation**:
  - **Speech-to-Text (STT)**: Offline speech recognition powered by Vosk.
  - **On-Device Translation**: Low-latency translation between Indian languages (Hindi, Tamil, Telugu, Kannada, Bengali, Marathi, Gujarati, etc.) and English using ML Kit.
  - **Text-to-Speech (TTS)**: Voice playback of received and translated messages in the user's preferred language.

- **📦 Ultra-Compact Protocol Buffers (Protobuf)**:
  - Messages encoded using lightweight binary schemas (`itantra.proto`) to maximize throughput over low-bitrate radio links.
  - Built-in acknowledgment system (`ITantraAck`) and envelope metadata (`ITantraEnvelope`).

- **📱 Modern Jetpack Compose UI**:
  - Fluid, responsive interface built with Jetpack Compose & Material 3.
  - Dashboard, Contact Discovery, Room Management, Live Chat Rooms, Audio Controls, and History.

- **💾 Local Persistence & Security**:
  - Room Database for conversation logs, audit trails, and offline message caching.
  - Device profiling and permission handling.

---

## 🛠️ Architecture & Tech Stack

| Layer | Technologies / Libraries |
|---|---|
| **UI** | Android Jetpack Compose, Material 3, Activity Compose |
| **Language & Tooling** | Kotlin, Gradle Kotlin DSL (`build.gradle.kts`), KSP |
| **Networking & Transport** | Google Play Services Nearby Connections, Wi-Fi Direct |
| **Serialization** | Google Protocol Buffers (Protobuf Lite for Kotlin & Java) |
| **Speech & AI** | Vosk Android SDK (STT), Google ML Kit (Translate & Language ID), Android TTS |
| **Storage** | AndroidX Room, DataStore Preferences |
| **Concurrency** | Kotlin Coroutines, StateFlow, Flow |

---

## 📂 Project Structure

```
iTantra/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/itantra/
│   │   │   │   ├── ai/               # STT, Translation, TTS engines
│   │   │   │   ├── deviceprofile/    # Hardware and device profiling
│   │   │   │   ├── protocol/         # Protobuf message handling and envelope factory
│   │   │   │   ├── security/         # Security and verification
│   │   │   │   ├── storage/          # Room Database & MessageRepository
│   │   │   │   ├── transport/        # Nearby Connections, BLE, Wi-Fi Direct
│   │   │   │   ├── ui/               # Compose UI, themes, and screens
│   │   │   │   └── MainActivity.kt   # Core application entry and navigation
│   │   │   ├── proto/
│   │   │   │   └── itantra.proto     # Protocol Buffer definitions
│   │   │   └── AndroidManifest.xml
│   │   └── test/
│   └── build.gradle.kts
├── gradle/
│   └── libs.versions.toml            # Version catalog
├── build.gradle.kts
└── settings.gradle.kts
```

---

## ⚙️ Getting Started

### Prerequisites
- Android Studio Hedgehog (2023.1.1) or newer
- JDK 17 or higher
- Android SDK 35 (compileSdk: 35, minSdk: 24)
- Two or more Android devices for testing peer-to-peer Nearby Connections

### Build & Run
1. Clone the repository:
   ```bash
   git clone https://github.com/madhavanp2025aids/iTantra--Indian-Multilingual-TTS-STT-Aided-Neural-Transceiver-Radio-Access-for-low-bitrate-links.git
   ```
2. Open the project in Android Studio.
3. Sync project with Gradle files.
4. Connect your Android device (ensure Bluetooth, Location, and Wi-Fi permissions are enabled).
5. Build and run the app:
   ```bash
   ./gradlew assembleDebug
   ```

---

## 📄 License

This project is licensed under the terms specified within this repository.
