The Air Quality Monitoring System operates through the following process:

* Gas Detection: The MQ135 sensor detects various gases and provides analog readings
* Environmental Sensing: DHT11 measures temperature and humidity
* Data Processing: Arduino processes sensor data and maps gas levels to AQI categories
* Display Output: Real-time data is displayed on the OLED screen
* Continuous Monitoring: The system updates readings in real-time

Components Required

| Component | Quantity | Description |
|-----------|----------|-------------|
| Arduino Uno | 1 | Main microcontroller board |
| MQ135 Gas Sensor | 1 | For detecting various gases and air pollutants |
| DHT11 Sensor | 1 | Temperature and humidity sensor |
| OLED Display (128x64) | 1 | SSD1306-based display for visual output |
| Breadboard | 1 | For prototyping connections |
| Jumper Wires | Several | For making connections |
| Power Supply | 1 | 5V power source for Arduino |

Pin Configuration

| Arduino Pin | Connected Component | Wire Color (Suggested) |
|-------------|-------------------|----------------------|
| A0 | MQ135 Analog Output | Yellow |
| D2 | DHT11 Data Pin | Blue |
| A4 (SDA) | OLED SDA | Green |
| A5 (SCL) | OLED SCL | White |
| 5V | VCC (All Components) | Red |
| GND | Ground (All Components) | Black |

Air Quality Index (AQI) Scale:

AQI Range	Category	Health Impact	Color Code:
| AQI Range | Category | Health Impact | Color Code |
|-----------|----------|---------------|------------|
| 0-50 | Good | Minimal impact | Green |
| 51-100 | Moderate | Acceptable for most people | Yellow |
| 101-150 | Unhealthy for Sensitive Groups | Sensitive individuals may experience symptoms | Orange |
| 151-200 | Unhealthy | Everyone may experience health effects | Red |
| 201-300 | Very Unhealthy | Health warnings for emergency conditions | Purple |
| 301-500 | Hazardous | Health alert - serious effects for everyone | Maroon |

Project AQI Mapping:

* < 151: Good Air Quality
* 151-200: Poor Air Quality
* 200-300: Very Bad Air Quality
* 300-500: Toxic Air Quality
* > 500: Extremely Toxic
