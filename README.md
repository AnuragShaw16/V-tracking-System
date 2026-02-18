🚗 Vehicle Tracking System (IoT + Web App)

An IoT-based real-time vehicle tracking system that monitors a vehicle’s live location using GPS + GSM + ESP32 and visualizes it on a web dashboard with Mapbox Maps.

The system continuously collects latitude & longitude from the GPS module, sends it to the cloud server using GPRS, stores it in ThingSpeak, and displays the live position on a web interface.

📌 Features

Real-time vehicle location tracking

Live map visualization

Location history tracking

Remote monitoring from anywhere

Login-protected dashboard

Automatic coordinate update every few seconds

Works without Wi-Fi (uses GSM network)

🧠 How It Works

GPS module fetches latitude & longitude from satellites

ESP32 reads coordinates

GSM module sends data to ThingSpeak via GPRS

Web server fetches data using API

Mapbox displays the live vehicle location

📡 Data Flow:

Vehicle → GPS → ESP32 → GSM (GPRS) → ThingSpeak Cloud → Web Server → Map Dashboard

🛠️ Tech Stack
Hardware

ESP32 Dev Board

Neo-6M GPS Module

SIM900A GSM Module

Voltage Regulators (7805, 7812)

Power Supply / Battery

Software

Arduino IDE (Embedded code)

PHP (Backend)

Mapbox API (Map visualization)

ThingSpeak API (Cloud data storage)

HTML / CSS / JS (Frontend)

000webhost (Hosting)

📂 Project Structure
Vehicle-Tracking-System/
│
├── hardware/
│   ├── main.ino              # ESP32 code
│
├── web/
│   ├── login.php
│   ├── logout.php
│   ├── geolocation.php       # Map dashboard
│
├── docs/
│   ├── circuit-diagram
│   ├── block-diagram
│
└── README.md

⚙️ Setup Instructions
1️⃣ Hardware Setup

Connect GPS TX → ESP32 RX

Connect GSM TX → ESP32 RX2

Power GSM module with external supply (Important!)

Insert SIM with data plan

2️⃣ Arduino Configuration

Install libraries:

TinyGPS++
SoftwareSerial


Update in code:

api_key = "YOUR_THINGSPEAK_API_KEY";
APN = "YOUR_SIM_APN";


Upload code to ESP32.

3️⃣ ThingSpeak Setup

Create a channel

Enable fields:

Field 1 → Latitude

Field 2 → Longitude

Copy Write API Key into Arduino code

4️⃣ Mapbox Setup

Replace in geolocation.php:

mapboxgl.accessToken = "YOUR_MAPBOX_TOKEN";

5️⃣ Web Hosting

Upload web/ folder to hosting server
(Default tested on 000webhost)

🔐 Login Credentials (Demo)
Username: admin@gmail.com
Password: admin123


(Change in login.php before deployment)

📊 Use Cases

Fleet management

Anti-theft tracking

School bus monitoring

Logistics companies

Accident detection systems (future scope)

🚀 Future Improvements

Mobile app integration

Push notifications

Geofencing alerts

Speed monitoring

Accident detection sensors

Multiple vehicle tracking

🧩 Challenges Faced

GSM network latency

GPS accuracy in dense areas

Power stability for SIM900A

Real-time refresh optimization
