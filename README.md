
# Annai Mira College Bus Tracking App 🚌

A mobile-first real-time college bus tracking and route management application built with **Flutter** and **Dart**. This application allows students to view active bus routes, check ordered stops dynamically for morning and evening travel modes, and track bus locations in real-time.

---

## 📋 Table of Contents
1. [Prerequisites](#1-prerequisites)
2. [Flutter Installation & Environment Setup](#2-flutter-installation--environment-setup)
3. [Android Command-Line Tools Configuration](#3-android-command-line-tools-configuration)
4. [Project Folder Structure](#4-project-folder-structure)
5. [Getting Started & Dependencies](#5-getting-started--dependencies)
6. [Running the App on an Emulator](#6-running-the-app-on-an-emulator)
7. [Important Notes](#7-important-notes)

---

## 1. Prerequisites

Before you begin, ensure your development machine meets the following requirements:

- **Operating System:** Windows 10/11, macOS, or Linux.
- **Hardware:** Minimum 8GB RAM (16GB recommended) with hardware virtualization enabled in BIOS.
- **Tools:** Git, Android Studio (or VS Code), and the Android SDK.

---

## 2. Flutter Installation & Environment Setup

### Step A: Download Flutter SDK

1. Visit the official Flutter installation guide and download the latest stable release for your OS.
   - **URL:** https://docs.flutter.dev/get-started/install
2. Extract the downloaded archive and place the files in a suitable location:
   - Windows example: `C:\src\flutter`
   - macOS/Linux example: `/Users/<username>/development/flutter`

### Step B: Configure Environment Variables (PATH)

To run Flutter commands from any terminal, add the Flutter `bin` directory to your `PATH`.

#### Windows
1. Open **Environment Variables** from Windows search.
2. Click **Edit the system environment variables**.
3. Click **Environment Variables...**.
4. Under **User variables** or **System variables**, select `Path` and click **Edit**.
5. Click **New** and add `C:\src\flutter\bin`.
6. Click **OK** and restart your terminal.

#### macOS / Linux
1. Open your shell profile file, such as `~/.bashrc`, `~/.zshrc`, or `~/.bash_profile`.
2. Add the following line, replacing the path with your Flutter installation location:

```bash
export PATH="$PATH:/Users/<username>/development/flutter/bin"
```

3. Save the file and reload your terminal profile:

```bash
source ~/.zshrc
```

---

## 3. Android Command-Line Tools Configuration

To build and run the app on Android emulators, configure the Android SDK and command-line tools.

1. Install Android Studio from https://developer.android.com/studio.
2. Open Android Studio and go to **Tools > SDK Manager**.
3. In **SDK Platforms**, ensure at least one Android SDK version is selected (for example, Android 14.0 / API 34).
4. In **SDK Tools**, enable for this path (C:\Users\lokesh\AppData\Local\Android\Sdk):
   - Android SDK Command-line Tools (latest)
   - Android SDK Build-Tools
5. Click **Apply** to install the chosen tools.

### Accept Android Licenses

Run the following command in a terminal:

```bash
flutter doctor --android-licenses
```

### Verify Your Setup

Run:

```bash
flutter doctor
```

Fix any issues reported by `flutter doctor` before continuing.

---

## 4. Project Folder Structure

The project follows a clean, modular structure separating models, screens, and network services:

```text
lib/
  main.dart
  models/
    bus_model.dart          # Data entities for routes and stops
  screens/
    home_screen.dart        # Main dashboard with morning/evening mode controls
    tracking_screen.dart    # Live map tracking screen
    stops_bottom_sheet.dart # Ordered stop list for selected routes
  services/
    api_service.dart        # API client and backend communication
pubspec.yaml                # Flutter dependencies and assets
README.md                   # Project documentation
```

## 4.1 How the App Works

- `main.dart` initializes the app and loads the main screen.
- `home_screen.dart` shows the list of available routes and the current travel mode.
- Selecting a route opens tracking details and the stop schedule.
- `tracking_screen.dart` displays a map with the current bus position and route path.
- `stops_bottom_sheet.dart` shows an ordered list of stops for the selected route.
- `api_service.dart` fetches route, bus location, and stop data from the backend.

## 4.2 Where to Make Changes

- Update data models in `lib/models/bus_model.dart` when route or stop structures change.
- Modify UI screens in `lib/screens/` to change app layout or user interactions.
- Adjust network requests in `lib/services/api_service.dart` if the API changes.

---

## 5. Getting Started & Dependencies

1. Clone the repository:

```bash
git clone <repository-url>
cd fluttermobileapp
```

2. Install dependencies:

```bash
flutter pub get
```

3. Verify the project setup:

```bash
flutter pub outdated
flutter doctor
```

---

## 6. Running the App on an Emulator

### Launch an Android Emulator

1. Open Android Studio and go to **Tools > Device Manager**.
2. Create a virtual device (for example, Pixel 6 with Android API 34).
3. Start the emulator using the **Play** button.

Alternatively, launch an emulator from the terminal:

```bash
flutter emulators
flutter emulators --launch <emulator_id>
```

### Run the Application

With the emulator running, run:

```bash
flutter run
```

### Hot Reload / Hot Restart

While the app is running in the terminal:

- Press `r` for Hot Reload
- Press `R` for Hot Restart

---

## 7. Important Notes

- This README is designed for easy understanding by anyone copying this folder.
- Open the project root in VS Code or Android Studio to edit and run the app.
- There is no `.env` file in this workspace by default.
- If the app requires API keys or tokens, store them securely and do not commit them to source control.
- Use `flutter clean` to remove build artifacts before rebuilding.

## 7.1 Quick Troubleshooting

- If `flutter doctor` reports missing tools, install the missing SDK components or accept licenses.
- If the emulator does not start, confirm the virtual device exists in Android Studio Device Manager.
- If the app fails to build, run `flutter clean` and then `flutter pub get` before retrying.
- If map or location data is unavailable, verify the API service URL and network connectivity.

---

## Contribution

Contributions are welcome. Improve documentation, add features, fix bugs, or update UI/UX behavior as needed.
