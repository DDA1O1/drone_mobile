# Drone Control React Native App

This is a React Native application designed to control a DJI Tello drone.

## Features

*   **Live Video Stream:** View the drone's camera feed in real-time.
*   **Flight Status:** Monitor battery level and flight time.
*   **Flight Controls:** 
    *   Virtual Joysticks for manual control (Yaw, Throttle, Pitch, Roll).
    *   Buttons for automated commands (Takeoff, Land, Emergency Stop).
*   **Media Capture (Simulated):** Buttons to simulate photo capture and video recording.
*   **Error Display:** Shows connection and command errors.
*   **Landscape Orientation Lock:** Ensures the app stays in landscape mode.

## Tech Stack

*   **Framework:** React Native
*   **State Management:** Redux Toolkit
*   **Drone Communication:** `react-native-udp` for sending commands and receiving status updates.
*   **Video Display:** `react-native-video` (likely used for the stream).
*   **UI Components:** `react-native-svg` (for joystick), `react-native-gesture-handler`.
*   **Video Processing:** `ffmpeg-kit-react-native` (potential usage for recording/processing).
*   **Orientation:** `react-native-orientation-locker`.

## Prerequisites

*   **Node.js:** Version 18 or higher (check `package.json` engines).
*   **React Native Environment:** Follow the official [React Native Set Up Your Environment guide](https://reactnative.dev/docs/set-up-your-environment) for your development OS and target platform (Android/iOS).
*   **Watchman:** Recommended file watcher for React Native.
*   **Android:** Android Studio, SDK, Emulator/Device.
*   **iOS:** Xcode, CocoaPods (installed via Bundler), Simulator/Device.
*   **DJI Tello Drone:** The drone itself.

## Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd drone_mobile
    ```
2.  **Install JavaScript dependencies:**
    ```bash
    npm install
    # OR
    # yarn install 
    ```
3.  **Install iOS Native Dependencies (if developing for iOS):**
    *   Install Bundler (if you don't have it):
        ```bash
        gem install bundler
        ```
    *   Install CocoaPods using Bundler:
        ```bash
        bundle install 
        ```
    *   Install Pods:
        ```bash
        cd ios
        bundle exec pod install
        cd ..
        ```

## Running the App

1.  **Connect to Tello Wi-Fi:** Connect your development machine or device to the Tello drone's Wi-Fi network (e.g., `TELLO-XXXXXX`).

2.  **Start the Metro Bundler:**
    Open a terminal in the project root and run:
    ```bash
    npm start
    # OR
    # yarn start
    ```

3.  **Build and Run on a Platform:**
    Keep the Metro bundler running. Open a *new* terminal in the project root.

    *   **Android:**
        ```bash
        npm run android
        # OR
        # yarn android
        ```
    *   **iOS:**
        ```bash
        npm run ios
        # OR
        # yarn ios
        ```

4.  **Connect in the App:** Once the app loads, tap the 'Connect & Stream' button.

## Controls

*   **Left Joystick:** Controls Yaw (Left/Right) and Throttle (Up/Down).
*   **Right Joystick:** Controls Roll (Left/Right) and Pitch (Forward/Backward).
*   **Buttons:** Use the dedicated buttons for Takeoff, Land, and Emergency Stop.

## Project Structure

```
.
├── android/          # Android native project
├── ios/              # iOS native project
├── src/
│   ├── components/   # Reusable UI components (Buttons, Status, Joystick, etc.)
│   ├── screens/      # App screens (MainScreen)
│   ├── services/     # Modules for external interactions (Tello, FFmpeg, Orientation)
│   └── store/        # Redux store setup (slice, store config)
├── App.js            # Main App component entry point
├── index.js          # React Native entry point
├── package.json      # Project dependencies and scripts
└── README.md         # This file
```
