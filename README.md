# 🎓 GEHU Attendance Intelligence & Smart QR System

An integrated suite of applications designed to modernize attendance tracking and management for students and faculty at Graphic Era Hill University (GEHU). 

This repository contains two core components:
1. **Bunk Calculator:** A client-side ERP enhancer that gives students real-time, gamified attendance intelligence[cite: 3].
2. **AttendQR:** A real-time, Firebase-powered smart attendance system for teachers and students using QR scanning technology.

---

## 📱 Part 1: Bunk Calculator (Student ERP Enhancer)
<p align="center">
  <img src="Screenshot 2026-05-04 180907.png" alt="DKAP Assists Model Selection" width="500">
  <br>
  <em>The model selection interface powered by Puter.js, providing access to 400+ AI models.</em>
</p>
<p align="center">
  <img src="Screenshot 2026-05-04 180907.png" alt="DKAP Assists Model Selection" width="500">
  <br>
  <em>The model selection interface powered by Puter.js, providing access to 400+ AI models.</em>
</p>
<p align="center">
  <img src="Screenshot 2026-05-04 180907.png" alt="DKAP Assists Model Selection" width="500">
  <br>
  <em>The model selection interface powered by Puter.js, providing access to 400+ AI models.</em>
</p>

Bunk Calculator is a native Android application built specifically for students of Graphic Era Hill University (GEHU)[cite: 3]. It wraps the university's existing ERP portal inside a WebView and silently augments it with an intelligent JavaScript-based overlay[cite: 3]. 

Without requiring official API access or server-side changes, it reverse-engineers the ERP's private attendance API to deliver real-time, subject-wise attendance tracking, bunk credit calculations, and goal-oriented reminders[cite: 3].

### ✨ Key Features
* **Zero-Input Tracking:** Provides instant, per-subject bunk credit calculation without requiring any manual input[cite: 3].
* **Recovery Estimator:** Calculates exactly how many consecutive classes a student must attend to recover from an attendance deficit (below 75%)[cite: 3].
* **Gamified Bunk Meter:** Displays attendance health using intuitive color-coded indicators (SAFE 🟢, OK 🔵, AT RISK 🟡, DANGER 🔴)[cite: 3].
* **Three-Lens View System:** Organizes data into an 'Overview' tab, a 'Bunk' tab (sorted by available credits), and a 'Needed' tab (sorted by urgency)[cite: 3].
* **Offline Capable:** Functions fully offline after the first data load within an active session[cite: 3].

### 🧮 Core Algorithms
All calculations run entirely on the client side[cite: 3].
* **Safe Bunk Calculation:** `Bunks = floor(Attended / 0.75 - Total)`[cite: 3]
* **Recovery Calculation:** `Classes Needed = ceil((0.75 * Total - Attended) / 0.25)`[cite: 3]

### 🔒 Security & Architecture
* The app acts as a transparent ERP client, inheriting the student's authenticated session (cookies) directly from the WebView[cite: 3].
* It makes a secure, same-origin `POST` request using `credentials:include` to fetch data[cite: 3].
* Passwords are never stored, no data is sent to third-party servers, and the application only reads data without modifying official records[cite: 3].

---

## 👨‍🏫 Part 2: AttendQR (Smart Teacher & Student System)

<p align="center">
  <img src="Screenshot 2026-05-04 181314.png" alt="Teacher side" width="500">
  <br>
  <em>The model selection interface powered by Puter.js, providing access to 400+ AI models.</em>
</p>AttendQR eliminates manual roll calls by creating a seamless, real-time connection between a Teacher's dashboard and the students' smartphones using Firebase Realtime Database.

### ✨ Key Features
* **Teacher Portal (Web):** A dark-themed, interactive dashboard that allows teachers to generate secure, unique QR codes for live class sessions.
* **Smart Payload:** The QR code contains a secure JSON payload with a unique `sessionId`.
* **Student Scanner App (Android):** Students use a dedicated Android app utilizing Google's ML Kit and CameraX to scan the teacher's QR code.
* **Instant Sync:** Upon scanning, the student app instantly pushes their Name, Roll Number, and Timestamp to the Firebase Realtime Database.
* **Live Dashboard Updates:** The Teacher Portal listens to the Firebase database and automatically populates the "Live Entries" list the second a student scans the code.

### 🛠️ Technology Stack
* **Student App (Bunk Calculator & Scanner):** Kotlin, AndroidX AppCompat, WebView API, CameraX, Google ML Kit Vision[cite: 3].
* **Teacher Portal:** HTML5, CSS3, Vanilla JavaScript, QRCode.js.
* **Backend & Sync:** Firebase Realtime Database (`asia-southeast1` region).
* **Data Processing:** Pure JavaScript for the ERP overlay[cite: 3].

---

## 🚀 Future Roadmap
* **Push Notifications:** Add daily reminders if any subject drops below an 80% buffer to warn students before they hit the critical 75% threshold[cite: 3].
* **Attendance Forecasting:** Project future attendance based on the semester calendar and remaining classes[cite: 3].
* **Android Widget:** Create a home-screen widget showing overall attendance percentage at a glance[cite: 3].
* **Historical Tracking:** Store weekly snapshots locally to graph attendance trends over time[cite: 3].
* **Multi-University Support:** Abstract the API layer to support ERPs at other Graphic Era campuses[cite: 3].

---
*Built with ❤️ for GEHU Students by Divyanshu Kaprawan (2026)*[cite: 3]
