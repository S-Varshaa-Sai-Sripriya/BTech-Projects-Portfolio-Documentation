# Gas Leakage Detection System using LM324 Op-Amp and MQ-6 Sensor  

## Project Overview  
This project implements a gas leakage detection system that identifies hazardous LPG leaks using an MQ-6 gas sensor and LM324 operational amplifier. The system triggers visual (LED) and audible (buzzer) alerts upon detecting gas concentrations above a safe threshold, enhancing safety in homes and industrial settings.  

## Key Features  
- **Real-time Gas Detection**: MQ-6 sensor detects LPG leaks and converts gas concentration to analog voltage.  
- **Comparator Circuit**: LM324 op-amp compares sensor output with a preset reference voltage to determine leakage.  
- **Instant Alerts**: Activates red LEDs and buzzer upon gas detection.  
- **Power Management**: Uses LM7805 voltage regulators to provide stable 5V supply for sensitive components.  
- **Fail-safe Indicators**: Green LED indicates normal operation; red LEDs + buzzer signal leakage.  

## Components Used  
| Category | Components |  
|----------|------------|  
| **Power Supply** | 12V adapter, bridge rectifier (W04), 1000µF capacitor, LM7805 voltage regulators |  
| **Sensing & Control** | MQ-6 gas sensor, LM324 op-amp, 10K preset potentiometer |  
| **Indicators** | Red/Green LEDs, 5V buzzer |  
| **Switching** | BC547 transistor, push-button switch |  
| **Miscellaneous** | PCB board, jumper wires, 14-pin DIP socket |  

## Working Principle  
1. **Step-down & Rectification**: 230V AC is converted to 12V DC via transformer and bridge rectifier.  
2. **Voltage Regulation**: LM7805 ICs regulate 12V DC to 5V for the MQ-6 sensor and op-amp.  
3. **Gas Sensing**: MQ-6 outputs analog voltage proportional to gas concentration.  
4. **Comparator Action**: LM324 compares sensor voltage with preset reference. If sensor voltage exceeds reference, the output goes high.  
5. **Alert Activation**: High output triggers BC547 transistor, activating buzzer and red LEDs.  

## Applications  
- **Household Safety**: Detects LPG leaks in kitchens.  
- **Industrial Monitoring**: Identifies gas leaks in factories/storage units.  
- **Automotive**: Monitors fuel leaks in vehicles.  
- **Portable Devices**: Can be integrated into handheld detectors for fieldwork.  

## Future Enhancements  
- **IoT Integration**: Send alerts via SMS/email using Wi-Fi/GSM modules.  
- **Automatic Shut-off**: Solenoid valve to cut gas supply during leaks.  
- **Multi-Gas Detection**: Expand sensor array for methane, propane, etc.  
- **Data Logging**: Record gas levels over time for analysis.  

## Link
[https://www.facebook.com/watch/?v=1783372128508215](https://www.facebook.com/watch/?v=1783372128508215)

## Getting Started  
1. Assemble components on PCB as per the circuit diagram.  
2. Calibrate the 10K preset to set leakage threshold.  
3. Power the system via 12V adapter.  
4. Test using a controlled gas source (e.g., lighter gas).  

## Acknowledgments  
- **Dr. Ilango Karuppasamy** (Faculty Guide, Amrita Vishwa Vidyapeetham)  
- **Amrita Vishwa Vidyapeetham, Chennai** for project support.  
