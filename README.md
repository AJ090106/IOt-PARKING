🚗 IoT-Based Smart Parking System
📌 Overview
The IoT-Based Smart Parking System is an intelligent parking management solution designed to monitor parking slot occupancy in real time using ESP32, HC-SR04 Ultrasonic Sensors, and a modern React.js Dashboard. The system continuously detects vehicle presence and updates the parking status instantly through WebSocket communication, enabling users and administrators to view live parking availability from anywhere.

Traditional parking systems often suffer from inefficient space utilization and lack of real-time monitoring. This project addresses these challenges by providing an automated, scalable, and responsive parking management platform.

🎯 Features
🚘 Real-time parking slot occupancy detection
📡 Wireless communication using ESP32 Wi-Fi capabilities
⚡ Instant dashboard updates via WebSockets
📊 Interactive React-based monitoring dashboard
🔄 Automatic status synchronization between hardware and frontend
📱 Responsive user interface for desktop and mobile devices
🟢 Visual indication of occupied and vacant parking slots
📈 Scalable architecture for multiple parking spaces
🏗️ System Architecture
+----------------+
| HC-SR04 Sensor |
+--------+-------+
         |
         v
+----------------+
|     ESP32      |
| (Arduino IDE)  |
+--------+-------+
         |
      Wi-Fi
         |
         v
+----------------+
| WebSocket      |
| Server         |
+--------+-------+
         |
         v
+----------------+
| React Dashboard|
+----------------+
🛠️ Tech Stack
Hardware
ESP32 Development Board
HC-SR04 Ultrasonic Sensor
Jumper Wires
Breadboard
USB Power Supply
Software
Arduino IDE
React.js
JavaScript
HTML5
CSS3
WebSocket Protocol
Node.js (Optional Backend Server)
⚙️ Working Principle
1. Vehicle Detection
The HC-SR04 Ultrasonic Sensor continuously measures the distance between the sensor and any object above it.

Distance calculation:

Distance = (Time × Speed of Sound) / 2
If the measured distance falls below a predefined threshold, the parking slot is marked as Occupied; otherwise, it is marked as Available.

2. Data Processing on ESP32
The ESP32:

Reads sensor measurements
Determines parking slot status
Connects to Wi-Fi
Sends parking updates to the WebSocket server
Example Status:

{
  "slot": 1,
  "status": "occupied"
}
3. Real-Time Communication
WebSockets provide a persistent communication channel between:

ESP32
Server
React Dashboard
Unlike HTTP polling, WebSockets eliminate repeated requests and provide:

Lower latency
Faster updates
Reduced bandwidth consumption
4. Dashboard Visualization
The React Dashboard receives live WebSocket messages and updates the UI instantly.

Example Display:

Slot 1 : Occupied 🔴
Slot 2 : Available 🟢
Slot 3 : Occupied 🔴
Slot 4 : Available 🟢
🔌 Hardware Connections
HC-SR04 to ESP32
HC-SR04 Pin	ESP32 Pin
VCC	5V
GND	GND
TRIG	GPIO 5
ECHO	GPIO 18
Pin numbers can be modified according to project requirements.

🚀 Installation & Setup
Clone Repository
git clone https://github.com/yourusername/iot-smart-parking-system.git

cd iot-smart-parking-system
ESP32 Setup
Install Arduino IDE.

Install ESP32 Board Package.

Install required libraries:

WiFi.h
WebSocketsClient.h
Upload the firmware to ESP32.

Update Wi-Fi credentials:

const char* ssid = "YOUR_WIFI";
const char* password = "YOUR_PASSWORD";
React Dashboard Setup
Install dependencies:

npm install
Run the application:

npm start
Dashboard will be available at:

http://localhost:3000
📂 Project Structure
Smart-Parking-System/
│
├── esp32/
│   ├── parking_system.ino
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
│
├── server/
│   ├── websocket-server.js
│
├── assets/
│   ├── architecture.png
│
└── README.md
📊 Future Enhancements
Multiple parking slot support
Cloud database integration
Parking analytics and reports
Mobile application support
Vehicle number plate recognition
Reservation and booking system
Email/SMS notifications
Integration with smart city infrastructure
🎓 Learning Outcomes
Through this project, the following concepts were explored:

Internet of Things (IoT)
ESP32 Programming
Sensor Interfacing
Real-Time Communication
WebSocket Protocol
React.js Development
Dashboard Design
Full-Stack IoT Architecture
🔮 Applications
Smart Parking Lots
Shopping Malls
Universities and Colleges
Corporate Offices
Residential Complexes
Smart City Infrastructure
Public Parking Management