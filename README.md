# EyeSeeYou
EyeSeeYou is an Android application designed to enhance the autonomy and safety of individuals with visual impairments. By leveraging Augmented Reality (AR) and
AI, the app analyzes the surroundings in real-time to identify obstacles, detect changes in elevation (steps, pits), and provide immediate feedback through 
speech synthesis (TTS) and haptic vibrations on both the smartphone and Wear OS devices.

🇮🇹 This was our group project for the course "*Mobile and Social Sensing System*" course for the Master Degree in Artificial Intelligence and Data Engineering in University of Pisa.

## 📌 Key Features
* **Intelligent Obstacle Detection**: Utilizes ARCore Semantic and Depth APIs to identify and locate objects in the field of view, classifying them into spatial zones (Left, Center, Right, Walls, High, Low).

* **Elevation Analysis**: A dedicated StepDetector module analyzes ground geometry to alert users of upcoming steps (upward or downward) and potential hazards like pits.

* **Multimodal Feedback**:

  - 🗣️ Vocal Assistant: Contextual audio notifications describing obstacle positions and system status.

  - 📳 Haptic Feedback (Phone): Integrated vibrations for silent alerts and gesture confirmation.

  - ⌚️ Wear OS Integration: Support for smartwatches to receive vibration alerts directly on the wrist for a more discreet experience.

  - 👋 Gesture-Based Interface: A touch-control system using swipes allows users to quickly toggle functions (TTS, Vibration, AR Session) without needing to look at the screen.

* **Privacy & Performance**: Local processing of sensor data ensures rapid response times and protects user privacy.

## 🛠 Project Architecture
The project is structured into two main modules:

* ```app```: The core Android smartphone application.

* ```MainProcessor```: Orchestrates the analysis logic by unifying semantic and depth data.

* ```ObjectDetector```: Identifies object classes (people, vehicles, obstacles) and maps their spatial position.

* ```ArCoreManager```: Manages the ARCore session, optimizing frame rates and handling camera configurations like the torch.

* ```wear```: A dedicated Wear OS module that listens for alert signals from the phone and triggers the smartwatch's vibration motor.

## 📋 System Requirements
* **Android Version**: 7.0 (API level 24) or higher.

* **Hardware**: An ARCore-supported device. A depth sensor (ToF) is recommended for optimal performance.

* **Wear OS**: (Optional) A compatible smartwatch for remote haptic feedback.

## 🔧 Installation & Setup
1. **Clone the repository**:

```Bash
git clone https://github.com/your-username/eyeseeyou.git
```
2. **Import to Android Studio**: Open the project and wait for the Gradle sync to complete.

3. **Permissions**: The app requires Camera permissions for AR features and Vibrate permissions for haptic feedback.

4. **Build**: Deploy the app module to your smartphone and the wear module to your smartwatch.

## 🎮 Quick Controls (Gestures)
The app utilizes the following swipes on the main interface for rapid management:

➡️ Swipe Right: Toggle ARCore session (Pause/Resume).

⬅️ Swipe Left: Toggle phone vibration.

⬆️ Swipe Up: Toggle smartwatch vibration.

⬇️ Swipe Down: Toggle Vocal Assistant (TTS).

## 🛠 Technologies Used
Language: **Kotlin**.

AR Framework: **Google ARCore** (Depth & Semantic APIs).

Wearable: **Google Play Services Wearable**.

Graphics: **OpenGL ES** (via a custom SampleRender pipeline).

Dependency Management: **Gradle** with Version Catalogs.

---
*Developed with the goal of making the world more accessible, one step at a time.*
