# Air-Quality-Monitoring-System1

Arduino Air Quality Monitoring System

Overview
This project demonstrates how to build a comprehensive air quality monitoring system using Arduino. The system monitors environmental parameters, including gas levels, temperature, and humidity in real-time, providing accurate Air Quality Index (AQI) readings on an OLED display.

Table of Contents
Features
Components Required
Circuit Diagram
Pin Configuration
How It Works
Air Quality Index (AQI) Scale
Installation
Code Explanation
Troubleshooting
Future Enhancements
FAQ
License
Features
Real-time Monitoring: Continuous monitoring of air quality, temperature, and humidity
AQI Classification: Categorises air quality as Good, Poor, Very Bad, or Toxic
OLED Display: Clear visual representation of all sensor readings
Cost-effective: DIY solution using affordable components
Educational: Perfect for learning about environmental monitoring and Arduino programming
Customizable: Easy to modify and add additional sensors
Components Required
Component	Quantity	Description
Arduino Uno	1	Main microcontroller board
MQ135 Gas Sensor	1	For detecting various gases and air pollutants
DHT11 Sensor	1	Temperature and humidity sensor
OLED Display (128x64)	1	SSD1306-based display for visual output
Breadboard	1	For prototyping connections
Jumper Wires	Several	For making connections
Power Supply	1	5V power source for Arduino
Circuit Diagram
The system uses I2C communication for the OLED display and analog/digital pins for sensors:

OLED Display: Connected via I2C (SDA/SCL pins)
MQ135 Sensor: Analog output to A0 pin
DHT11 Sensor: Digital data pin to D2
Pin Configuration
Arduino Pin	Connected Component	Wire Color (Suggested)
A0	MQ135 Analog Output	Yellow
D2	DHT11 Data Pin	Blue
A4 (SDA)	OLED SDA	Green
A5 (SCL)	OLED SCL	White
5V	VCC (All Components)	Red
GND	Ground (All Components)	Black
How It Works
The Air Quality Monitoring System operates through the following process:

Gas Detection: The MQ135 sensor detects various gases and provides analog readings
Environmental Sensing: DHT11 measures temperature and humidity
Data Processing: Arduino processes sensor data and maps gas levels to AQI categories
Display Output: Real-time data is displayed on the OLED screen
Continuous Monitoring: The system updates readings in real-time
Air Quality Index (AQI) Scale
AQI Range	Category	Health Impact	Color Code
0-50	Good	Minimal impact	Green
51-100	Moderate	Acceptable for most people	Yellow
101-150	Unhealthy for Sensitive Groups	Sensitive individuals may experience symptoms	Orange
151-200	Unhealthy	Everyone may experience health effects	Red
201-300	Very Unhealthy	Health warnings for emergency conditions	Purple
301-500	Hazardous	Health alert - serious effects for everyone	Maroon
Project AQI Mapping
The system uses simplified thresholds based on sensor readings:

< 151: Good Air Quality
151-200: Poor Air Quality
200-300: Very Bad Air Quality
300-500: Toxic Air Quality
> 500: Extremely Toxic
Installation
Hardware Setup
Assemble Components: Connect all components according to the pin configuration table
Power Connections: Ensure all components share common 5V and GND connections
Sensor Placement: Position the MQ135 sensor in an area with good air circulation
Software Setup
Install Arduino IDE: Download from arduino.cc

Install Required Libraries:

Adafruit GFX Library
Adafruit SSD1306 Library
DHT Sensor Library
Upload Code: Copy the provided code and upload to your Arduino

Library Installation via Arduino IDE
Tools → Manage Libraries → Search for:
- "Adafruit GFX"
- "Adafruit SSD1306" 
- "DHT sensor library"
Code Explanation
Key Functions
air_sensor():

Reads analog values from MQ135 sensor
Maps readings to AQI categories
Displays gas level and quality status
sendSensor():

Reads temperature and humidity from DHT11
Handles sensor errors
Updates display with environmental data
setup():

Initializes serial communication
Configures OLED display
Shows startup messages
loop():

Continuously updates sensor readings
Refreshes display with current data
Sensor Calibration
The MQ135 sensor requires a warm-up period of 24-48 hours for accurate readings. Initial readings may be unstable until the sensor stabilizes.
