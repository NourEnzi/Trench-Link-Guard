# Trench-Shield 🛡️

> A lightweight, native Android intent-interceptor designed to catch and scan URLs from third-party apps (like WhatsApp) before they are loaded in the browser.

## 📖 Overview
Trench-Shield acts as a stealthy gatekeeper. It registers as a web browser on the Android system. When a user clicks a link in any messaging app, Trench-Shield silently intercepts the intent, scans the URL against threat intelligence APIs, and decides the routing logic in milliseconds. 

Clean links are seamlessly passed to the user's default browser, while malicious or phishing links trigger a full-screen warning, protecting the user from social engineering attacks.

## ✨ Features
- **Stealth Mode Execution**: No UI is rendered during the scanning phase to ensure a seamless and uninterrupted user experience.
- **Native Android Performance**: Built entirely with Kotlin and Coroutines for instant cold starts, zero battery drain in the background, and minimal memory footprint.
- **Cloud Threat Intelligence**: Integrates with modern Security APIs (e.g., VirusTotal) for real-time phishing and malware detection.
- **Zero-Friction Routing**: Automatically and transparently forwards safe intents to the actual web browser without manual user intervention.

## 🏗️ Architecture Workflow
1. **The Gatekeeper (`AndroidManifest.xml`)**: Utilizes custom `Intent Filters` to intercept `http` and `https` schemas globally across the OS.
2. **Invisible Interceptor (`ScanActivity.kt`)**: A `Theme.NoDisplay` activity receives the deep link in the background without freezing the current active application.
3. **Cloud Scanner**: Executes a non-blocking asynchronous HTTP request to verify the domain reputation.
4. **Routing Engine**: 
   - *Clean URL*: Fires a new Intent to open the target browser.
   - *Malicious URL*: Launches `WarningActivity` to block navigation and alert the user.

## 🛠️ Tech Stack
- **Language**: Kotlin
- **Concurrency**: Kotlin Coroutines
- **Networking**: OkHttp3 / Retrofit2
- **Architecture**: Native Android Components (Activities, Intents, System Filters)

## 🚀 Installation & Setup
*(Setup instructions and APK releases will be updated as the core modules are finalized).*

## 📄 License
This project is distributed under the MIT License. See the `LICENSE` file for more information.
