# Automatic Hand Sanitizer Dispenser using Arduino  

## Project Overview  
This project implements a touchless hand sanitizer dispenser using Arduino UNO, an ultrasonic sensor (HC-SR04), and a servo motor. The system detects hand proximity wirelessly and dispenses sanitizer without physical contact, promoting hygiene during the COVID-19 pandemic.  

## Key Features  
- **Touchless Operation**: HC-SR04 ultrasonic sensor detects hand presence within 5cm range.  
- **Automated Dispensing**: Servo motor pulls sanitizer nozzle when triggered.  
- **Cost-Effective**: Built with affordable components (Arduino UNO, servo motor, ultrasonic sensor).  
- **Public Health Focus**: Reduces surface contact to prevent virus transmission.  

## Components  
| Component         | Quantity | Purpose                                  |  
|-------------------|----------|------------------------------------------|  
| Arduino UNO       | 1        | Microcontroller for system control       |  
| HC-SR04 Sensor    | 1        | Detects hand proximity (2cm–400cm range) |  
| Servo Motor       | 1        | Mechanically pulls sanitizer nozzle      |  
| Jumper Wires      | As needed | Connects components to Arduino           |  
| USB Cable (Type B)| 1        | Uploads code to Arduino UNO              |  

## Working Principle  
1. **Detection**: HC-SR04 emits ultrasonic waves; if a hand is detected within 5cm, it triggers the servo.  
2. **Actuation**: Servo motor rotates 180°, pulling the sanitizer nozzle via attached wires.  
3. **Dispensing**: Sanitizer is released without touch. The system resets after use.  

## Arduino Code Snippet  
```cpp  
#include <Servo.h>  
#define echoPin 4  
#define trigPin 5  
Servo myservo;  
long duration;  
int distance;  

void setup() {  
  pinMode(trigPin, OUTPUT);  
  pinMode(echoPin, INPUT);  
  myservo.attach(3);  
}  

void loop() {  
  digitalWrite(trigPin, LOW);  
  delayMicroseconds(2);  
  digitalWrite(trigPin, HIGH);  
  delayMicroseconds(10);  
  digitalWrite(trigPin, LOW);  
  duration = pulseIn(echoPin, HIGH);  
  distance = duration * 0.034 / 2;  

  if (distance <= 5) {  
    myservo.write(180);  // Dispense sanitizer  
    delay(1000);  
  } else {  
    myservo.write(0);    // Reset position  
  }  
}  
```  

## Applications  
- **Public Spaces**: Schools, offices, malls, and hospitals.  
- **Healthcare**: Reduces contact in high-risk environments.  
- **IoT Integration**: Can be expanded with IoT for usage monitoring.  

## Advantages  
- **Hygienic**: Eliminates touchpoints.  
- **Low Power**: Operates on 5V (USB/battery-powered).  
- **Scalable**: Can be adapted for soap dispensers or other liquids.  

## Future Enhancements  
- **Battery Backup**: Enable portable operation.  
- **LCD Display**: Show sanitizer level/usage statistics.  
- **Multi-Nozzle System**: Serve multiple users simultaneously.  

## Acknowledgments  
- **Amrita Vishwa Vidyapeetham, Chennai** for academic support.  
- **Dr. A. Manikandan** (Faculty Guide) for project guidance.  

---  
*Note: Aligns with WHO hygiene guidelines to combat COVID-19 transmission.*
