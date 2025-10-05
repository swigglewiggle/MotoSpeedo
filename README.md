# MotoSpeedo - High-Precision GPS Performance Meter
MotoSpeedo is an advanced performance meter for your motorcycle or car, designed to provide accurate, repeatable acceleration timings and detailed run analysis.

Unlike a simple speedometer app, MotoSpeedo uses a combination of GPS and sensor data with intelligent calculation to deliver precise performance metrics, helping you track improvements and understand your vehicle's capabilities.

# Core Features
Accurate Performance Timing: Log key acceleration benchmarks, including 0-10, 0-20, 0-30, 0-40, 0-50, and 0-60 mph (or kph) times, as well as your top speed for each run.

Accelerometer Launch Trigger: For unparalleled precision, the timer starts the instant your phone's accelerometer detects launch movement. This eliminates the lag and inaccuracy of waiting for the first GPS speed reading. A 2-second fallback ensures the test always starts reliably.

Advanced Data Analysis: Every run is saved with detailed data. Review your performance with two separate graphs:

Speed vs. Time: A smooth curve showing your speed progression throughout the run.

Acceleration vs. Time: A detailed G-force graph showing the raw forces of your launch, gear shifts, and peak power delivery.

Cloud-Synced Personal Bests: When you sign in, your ultimate records are saved securely to the cloud. MotoSpeedo automatically updates your profile with your all-time fastest 0-30, 0-40, 0-60 times, and overall max speed. (Note: Only runs from a standing start are eligible for "fastest time" records).

Hands-Free Operation: Keep your hands on the controls. Use simple voice commands ("start," "stop") or your helmet's media buttons to control testing sessions safely.
**This feature was designed for the safety of motorcycle riders. You 0-top speed will be read out after u stop the run.**

Background Tracking: Thanks to a dedicated foreground service, your runs will continue to record accurately even if your screen turns off or you switch to another app.

Local Run History: A complete log of all your past runs is saved on your device, allowing you to access the detailed graphs for any run at any time.

Customizable Units: Switch between MPH and KPH to match your preference. The display and run logs will update accordingly.

# Screenshots

<img width="720" height="1600" alt="image" src="https://github.com/user-attachments/assets/bb515df5-147d-4837-ad86-01c1207da29e" />
<img width="720" height="1600" alt="image" src="https://github.com/user-attachments/assets/a03cce28-959b-46fa-acd7-742c33445edd" />
<img width="230" height="512" alt="image" src="https://github.com/user-attachments/assets/e5e8610f-7744-43d4-9629-fb4a7ebec071" />
<img width="230" height="512" alt="image" src="https://github.com/user-attachments/assets/6c162e30-d25c-4048-ab9a-48632841c120" />


How It Works: The Technology Behind the Accuracy
MotoSpeedo achieves high precision through a three-stage process:

The Start: Instead of relying on slow GPS, the app uses the phone's accelerometer to detect the exact moment of launch. The master timer starts at the final countdown beep using a high-resolution system clock (System.nanoTime()). If the phone doesnt detect any acceleraometer movement at the start then dont worry! the timer automatically starts after the beep.

The Run: A foreground service ensures the app maintains a high-priority connection to the device's GPS, collecting location and speed data at the fastest possible rate, even with the screen off.

The Finish: The app doesn't just stop the timer when you cross a target speed. It uses linear interpolation on the data points just before and after the target to calculate the exact fractional second you crossed the line, eliminating errors from the GPS update interval.

# Installation
You can install the app on your Android device by downloading the latest app-release.apk file.

Download the .apk file from the latest release.

Tap on the downloaded file in your phone's notification shade or file manager.

Your phone will show a security warning. Tap "Settings".

Find your browser or file manager in the list and enable the "Allow from this source" or "Install unknown apps" permission.

Go back and tap the .apk file again to install it.

This permission is only needed the first time you install an app from outside the Play Store.

Technology Stack
Language: Kotlin

UI: Android XML

Cloud Storage: Google Firebase Firestore (for personal bests)

Analytics: Google Firebase Analytics

Charting: MPAndroidChart
