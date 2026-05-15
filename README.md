# 🏥 Quadra Care Vital Sync System — Automated Patient Monitoring & Ventilation Control System

> **InnoFusion Hackathon Project** | Team: Aragya

---

## 📌 Overview

**Aragya** is an end-to-end smart healthcare system that monitors patient vitals in real time, stores readings against unique Patient IDs in a database, and **automatically controls ventilation** based on the sensor data. A companion web interface handles patient data collection and health surveys.

The system closes the loop between sensing and actuation — vitals are not just displayed but actively used to trigger ventilation adjustments, removing the need for constant manual intervention.

---

## ✨ Features

- **📡 Live Sensor Data Acquisition** — Arduino Uno and Nano continuously read patient vitals from connected sensors
- **🗄️ Patient-ID-Linked Storage** — All sensor readings are stored in a MySQL database tagged to individual Patient IDs for traceability and history
- **🌬️ Automated Ventilation Control** — Based on incoming sensor data, the system automatically actuates ventilation to maintain safe patient parameters
- **🌐 Patient Data Web Interface** — A responsive webpage for registering patients, collecting health data, and conducting surveys
- **📊 Real-Time Dashboard** — Live view of patient vitals and system status

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Hardware** | Arduino Uno, Arduino Nano, Sensors, Ventilation Actuator |
| **Firmware** | C / C++ (Arduino IDE) |
| **Frontend** | HTML, CSS, JavaScript |
| **Backend** | Node.js |
| **Database** | MySQL |

---

## 📁 Project Structure

```
InnoFusion_Aragya/
├── Aragya Webpage/          # Patient data collection & survey web interface
├── Aragya-Arduino Codes/    # Firmware for Uno and Nano (sensing + actuation)
├── Aragya-Patient DBMS/     # MySQL schema, Patient-ID-linked data storage
├── .gitignore
└── README.md
```

---

## 🔄 System Architecture

```
[Sensors] ──→ [Arduino Uno / Nano]
                      │
              ┌───────┴────────┐
              ↓                ↓
   [Ventilation Actuator]   [Backend / DBMS]
   (auto-controlled)        (stored by Patient ID)
                                   ↓
                         [Web Dashboard & Survey]
```

1. Sensors continuously read patient vitals
2. Arduino firmware processes the readings in real time
3. If readings cross thresholds → ventilation is automatically adjusted
4. All data is sent to the backend and stored against the patient's unique ID
5. The web interface lets staff register patients, view records, and run surveys

---

## ⚙️ Installation & Setup

### Prerequisites

- [Arduino IDE](https://www.arduino.cc/en/software)
- [Node.js and npm](https://nodejs.org/)
- MySQL (local or hosted)

### 1. Clone the Repository

```bash
git clone https://github.com/CODESSOHAM/InnoFusion_Aragya.git
cd InnoFusion_Aragya
```

### 2. Arduino Setup

1. Open Arduino IDE
2. Navigate to `Aragya-Arduino Codes/`
3. Load the appropriate `.ino` file for your board (Uno or Nano)
4. Connect your board via USB and upload the firmware

### 3. Database Setup

1. Start your MySQL server
2. Navigate to `Aragya-Patient DBMS/`
3. Import the schema:

```bash
mysql -u root -p < schema.sql
```

### 4. Web Interface Setup

```bash
cd "Aragya Webpage"
npm install
npm start
```

Open your browser at `http://localhost:3000`

---

## 🧰 Hardware Components

- Arduino Uno / Arduino Nano
- Vital signs sensors (ECG-AD8232, SpO2-MAX30102, etc.)
- Ventilation control actuator
- Steeper Motor-NIMA17
- Connecting wires and breadboard
- Ventilation Bag
- Oxygen cylinder

---

## 💡 Key Engineering Highlights

- **Closed-loop control** — the system doesn't just monitor; it acts on data automatically
- **Patient-ID-based data model** — every reading is traceable to a specific patient, enabling longitudinal health tracking
- **Multi-board firmware** — separate optimized firmware for Uno and Nano depending on role
- **Full-stack integration** — hardware, firmware, backend, database, and web UI all connected in one pipeline

---

## 👥 Team

**Team ARAGYA** — InnoFusion Hackathon

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
