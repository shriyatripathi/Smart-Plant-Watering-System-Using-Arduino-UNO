# Smart-Plant-Watering-System-Using-Arduino-UNO
Designed and developed an automated plant watering system that monitors soil moisture levels in real-time and waters the plant without requiring user intervention. The system sends SMS alerts to notify the user in case of dry soil or potential flooding.
Hardware Components
Arduino UNO
Acts as the central controller, reading moisture data and controlling the motor pump.

Soil Moisture Sensor
The sensor module includes both analog and digital outputs. It uses an LM393 comparator to compare the sensor reading with a user-defined threshold set via a potentiometer. In this project, the analog output is used to allow software-level calibration of the moisture threshold.

LED Indicators
Provide visual cues for different states such as low moisture, watering in progress, or normal moisture levels.

NodeMCU (ESP8266)
Handles wireless communication and sends SMS alerts to the user when the soil is too dry or flooding conditions are detected.

Motor Pump
Automatically waters the plant when soil moisture falls below a certain threshold and stops once adequate moisture is restored.

