# Temperature Controlled Fan using Microcontroller

## Project Overview
This project implements a temperature-controlled DC fan system using a microcontroller. The fan automatically turns ON/OFF based on ambient temperature readings from a sensor, providing an energy-efficient and automated cooling solution.

## Key Features
- **Automatic Temperature Control**: Fan activates when temperature exceeds a set threshold (e.g., 25°C)
- **Real-time Display**: 16x2 LCD shows current temperature readings
- **Energy Efficient**: Only operates when needed, reducing power consumption
- **Modular Design**: Can be adapted for various applications (CPUs, rooms, car engines)

## Components Used
| Category | Components |
|----------|------------|
| Microcontroller Section | AT89C51, 33pF capacitor, 10μΩ resistors, 10μF capacitor, push button, 16x2 LCD |
| Temperature Sensor | LM35 temperature sensor, 10K resistor, 150pF capacitor |
| Load Section | 2N2222 transistor, 1N4007 diode, relay, DC fan |

## Working Principle
1. LM35 sensor continuously monitors ambient temperature
2. Analog signal is converted to digital via ADC
3. Microcontroller processes the data and displays temperature on LCD
4. If temperature exceeds threshold, microcontroller activates relay to power fan
5. Fan turns off automatically when temperature drops below threshold

## Applications
- Computer CPU cooling
- Smart home automation
- Industrial equipment cooling
- Automotive engine temperature regulation
- Electronic component cooling

## Future Enhancements
- IoT integration for remote monitoring/control
- Multi-fan control for larger spaces
- Data logging capabilities
- Mobile app interface
- AI-based predictive cooling

## Contributors
- [S. Varshaa Sai Sripriya](mailto:your-email@example.com)

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments
- Dr. Ilango Karuppasamy (Faculty Guide)
- Amrita Vishwa Vidyapeetham
