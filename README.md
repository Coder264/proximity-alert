# 📍 Proximity Alert

A native Android app built with **Kotlin + Jetpack Compose** that acts as a GPS-based location alarm. Set a destination, define a radius, and get alerted with a loud alarm + vibration when you're nearby — even with the screen off.

## ✨ Features

- **🗺️ Map Picker** — Search places by name or tap to select on an interactive OpenStreetMap
- **📡 Real-time Tracking** — Live distance display with animated progress indicator
- **🔔 Loud Alarm** — System alarm at max volume + vibration pattern on arrival
- **⚙️ Background Service** — Foreground service keeps tracking with the screen off
- **🎯 Custom Radius** — Adjustable alert radius from 100m to 5km
- **🌙 Dark Theme** — Sleek Material 3 dark UI

## 📸 Screenshots

<!-- Add your screenshots here -->
<!-- ![Home Screen](screenshots/home.png) -->
<!-- ![Map Picker](screenshots/map.png) -->

## 🏗️ Architecture

```
MainActivity (ComponentActivity)
├── ProximityScreen (Compose UI)
│   ├── Distance Indicator (animated ring)
│   ├── Destination Input + Map Picker
│   ├── Radius Slider
│   └── Set/Stop Buttons
├── MapPickerScreen (OpenStreetMap + Nominatim Search)
├── ProximityViewModel (StateFlow)
└── LocationTrackingService (Foreground Service)
    ├── FusedLocationProvider (GPS)
    ├── AlarmPlayer (MediaPlayer + Vibrator)
    └── LocalBroadcastManager (distance updates)
```

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| Kotlin | Primary language |
| Jetpack Compose | Declarative UI |
| Material 3 | Design system |
| FusedLocationProvider | GPS tracking |
| Foreground Service | Background execution |
| osmdroid | OpenStreetMap tiles |
| Nominatim API | Geocoding / place search |
| ViewModel + StateFlow | State management |

## 🚀 Getting Started

### Prerequisites
- Android Studio (Hedgehog or newer)
- JDK 17
- Android device or emulator (API 26+)

### Build & Run
```bash
git clone https://github.com/YOUR_USERNAME/proximity-alert.git
cd proximity-alert/android
```
1. Open the `android/` folder in Android Studio
2. Wait for Gradle sync to complete
3. Connect your device → click **Run ▶️**
4. Grant location and notification permissions

## 📱 Usage

1. **Set Destination** — Enter coordinates manually or tap **"Pick on Map"**
2. **Adjust Radius** — Slide between 100m and 5km
3. **Start Tracking** — Tap **"Set Alarm"** — the app begins GPS tracking
4. **Get Alerted** — When you enter the radius, a loud alarm + vibration triggers
5. **Stop** — Tap **"Stop"** to silence and reset

## 📂 Project Structure

```
app/src/main/
├── java/com/proximityalert/
│   ├── MainActivity.kt          # Entry point, permissions, navigation
│   ├── ProximityViewModel.kt    # UI state management
│   ├── LocationTrackingService.kt # Foreground GPS service
│   ├── AlarmPlayer.kt           # Sound + vibration
│   └── ui/
│       ├── screens/
│       │   ├── ProximityScreen.kt   # Main UI
│       │   └── MapPickerScreen.kt   # Map destination picker
│       └── theme/
│           ├── Color.kt         # Color palette
│           └── Theme.kt         # Material 3 theme
└── res/
    ├── values/
    │   ├── colors.xml
    │   ├── strings.xml
    │   └── themes.xml
    └── drawable/
        └── ic_launcher*.xml     # App icon
```

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

Built with ❤️ using Kotlin & Jetpack Compose
