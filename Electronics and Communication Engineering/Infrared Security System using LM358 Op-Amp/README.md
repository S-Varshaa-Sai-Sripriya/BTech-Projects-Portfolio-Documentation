# Infrared Security System using LM358 Op-Amp  

## Project Overview  
This project implements an infrared-based security system that detects intruders using an IR transmitter-receiver pair and triggers an alert light via an LM358 comparator circuit. Designed for cost-effective property protection, the system activates when an object interrupts the IR beam, making it suitable for homes, banks, and restricted areas.  

## Key Features  
- **Intruder Detection**: IR transmitter-receiver pair detects object interruptions within line-of-sight range.  
- **Comparator Logic**: LM358 op-amp compares sensor input with a reference voltage to trigger alerts.  
- **Visual Alert**: ULN2803 relay driver activates a 12V bulb upon detection.  
- **Power Management**: LM7805 regulator provides stable 5V supply to sensitive components.  
- **Modular Design**: PCB-based assembly for easy deployment and scalability.  

## Components  
| Category | Key Components |  
|----------|----------------|  
| **Power Supply** | 12V adapter, LM7805 regulator, bridge rectifier, 1000µF capacitor |  
| **Sensing** | IR LED (transmitter), photodiode (receiver) |  
| **Signal Processing** | LM358 op-amp (comparator mode), 10K potentiometer |  
| **Output** | ULN2803 relay driver, 12V bulb, indicator LEDs |  
| **Miscellaneous** | PCB, jumper wires, 2-pin connectors |  

## Working Principle  
1. **IR Beam Setup**: The IR LED emits infrared light, which is detected by the photodiode under normal conditions.  
2. **Intruder Detection**: When an object interrupts the IR beam, the photodiode’s output voltage drops.  
3. **Voltage Comparison**: The LM358 compares this voltage with a preset reference (adjusted via 10K potentiometer).  
4. **Alert Activation**: If the sensed voltage exceeds the reference, the LM358 triggers the ULN2803 to power the alert bulb.  

## Applications  
- **Home Security**: Detects unauthorized entry at doors/windows.  
- **Commercial Use**: Protects jewelry shops, banks, and labs.  
- **Vehicle Protection**: Alerts against tampering.  
- **Smart Lighting**: Basis for automated streetlights.  

## Advantages  
- **Low Cost**: Uses affordable, off-the-shelf components.  
- **Energy Efficient**: Consumes minimal power in standby mode.  
- **Easy Installation**: Compact PCB design for flexible deployment.  

## Limitations  
- **Line-of-Sight**: Requires unobstructed IR beam alignment.  
- **Short Range**: Effective within ~5 meters (extendable with lenses).  
- **Non-Selective**: Cannot distinguish between humans/animals.  

## Future Enhancements  
- **GSM Integration**: Send SMS alerts via microcontroller.  
- **Camera Activation**: Sync with hidden cameras for visual verification.  
- **IoT Enablement**: Remote monitoring via Wi-Fi/Bluetooth.  

## Acknowledgments  
- **Dr. Ilango Karuppasamy** (Faculty Guide, Amrita Vishwa Vidyapeetham)  
- **Amrita School of Engineering, Chennai** for infrastructure support.  

