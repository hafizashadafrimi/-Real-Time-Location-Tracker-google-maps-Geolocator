# 📍 Real-Time Location Tracker

A Flutter-based Android application that displays the user's current location on Google Maps, automatically updates it every 10 seconds while the app is in the foreground, and visualizes location history using a blue polyline.

## ✨ Features

- **Google Maps Integration** — Displays an interactive Google Map and smoothly moves the camera to the user's current location.
- **Location Permissions** — Requests the required location permissions and handles GPS being disabled.
- **Automatic Location Updates** — Refreshes the current location every 10 seconds while the app is active.
- **Live Location Marker** — Updates the map marker and displays the latest latitude and longitude in its information window.
- **Route Visualization** — Draws a blue polyline connecting successive location updates, retaining up to the latest 1,000 points.
- **Recenter Control** — Quickly returns the map camera to the current location.
- **Manual Refresh** — Allows users to refresh their location on demand.
- **Lifecycle Management** — Pauses automatic updates when the app enters the background and resumes location checking when it returns to the foreground.

## 🛠️ Technologies Used

- **Flutter** — Cross-platform application framework
- **Dart** — Programming language
- **Google Maps SDK for Android** — Interactive map integration
- **`google_maps_flutter`** — Flutter Google Maps plugin
- **`geolocator`** — Location services and permission handling

## 📋 Prerequisites

Before running the application, make sure you have:

- Flutter SDK with a compatible Dart SDK (Dart 3.13 or newer, as required by the project)
- Android Studio or Visual Studio Code
- Android SDK and an Android emulator or physical Android device
- A Google Cloud project with billing enabled and Maps SDK for Android configured

## 🚀 Setup and Installation

### 1. Clone the Repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_PROJECT_DIRECTORY>
```

Replace the placeholders with your actual GitHub repository URL and project directory.

### 2. Configure Google Maps API

1. Open the [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project or select an existing project.
3. Enable **Maps SDK for Android**.
4. Set up billing and generate a Google Maps API key.
5. Restrict the API key to Maps SDK for Android and configure the Android application restriction.

Use the following Android application ID:

```text
com.example.google_map_assignment
```

Also add the appropriate SHA-1 signing certificate fingerprint to the Android app restriction.

To find the SHA-1 fingerprint, open a terminal in the project's `android` directory and run:

**Windows**

```bash
gradlew.bat signingReport
```

**macOS / Linux**

```bash
./gradlew signingReport
```

### 3. Add Your API Key

Open `android/local.properties` and add or update the following property:

```ini
MAPS_API_KEY=your_real_api_key_here
```

Replace `your_real_api_key_here` with your actual API key.

**Important:** Keep your existing `sdk.dir` and `flutter.sdk` properties. Never commit or publicly share your real API key.

### 4. Install Dependencies

From the project root, run:

```bash
flutter pub get
```

### 5. Analyze and Test

Run the following commands to check the project and execute its tests:

```bash
flutter analyze
flutter test
```

### 6. Run the Application

Connect a physical Android device with location services enabled, or configure a location in the Android Emulator.

Then run:

```bash
flutter run
```

## 📌 Important Notes

- A valid Google Maps API key and an enabled Maps SDK for Android are required to display map tiles.
- Location updates occur every 10 seconds while the application screen is active.
- Background location tracking is not implemented. The periodic timer pauses when the app enters the background.
- The blue polyline connects sampled GPS coordinates; it does not follow actual roads.
- Drawing road-following routes would require an appropriate routing or Directions API integration.
- Location accuracy depends on the device, GPS signal, and available location providers.

## 👩‍💻 Author

**Hafiza Shadaf Rimi**

Flutter Developer | Android Application Development

---

*Developed as a Flutter project to demonstrate Google Maps integration, real-time location updates, permission handling, and route visualization.*
