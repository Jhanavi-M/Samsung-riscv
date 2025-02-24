## Smart Home Automation using VSD Mini RISC-V and ESP8266

### Project Summary

The **Smart Home Automation** project is designed to enable remote control of home appliances using the **VSD Squadron Mini RISC-V board** and **ESP8266 Wi-Fi module**. This system allows users to operate LED bulbs wirelessly via the **Blynk app** by leveraging the processing power of the RISC-V microcontroller and the wireless communication capabilities of the ESP8266.

### Key Features
- **Remote Control:** Users can turn LED bulbs on or off from anywhere using the Blynk mobile app.
- **Wi-Fi Connectivity:** The ESP8266 module establishes a seamless connection between the VSD Squadron Mini and the Blynk cloud.
- **Real-time Feedback:** The app provides instant updates on the LED status.
- **Scalability:** This project can be expanded to control additional home appliances like fans or door locks.

### System Overview
The RISC-V microcontroller processes input signals from the Blynk app, relayed through the ESP8266 Wi-Fi module. Based on the received commands, the microcontroller toggles the GPIO pins connected to the LEDs, switching them on or off accordingly.

### Components Used
- **VSD Squadron Mini RISC-V Board**: Serves as the main controller for processing and executing commands.
- **ESP8266 Node MCU**: Manages wireless communication and links the microcontroller to the internet.
- **LEDs (x4)**: Represent home appliances controlled via the app.
- **Breadboard**: For circuit prototyping.
- **Jumper Wires**: For interconnections.

### Applications
- **Home Automation**: Remotely control appliances, ensuring convenience and energy efficiency.
- **Security Systems**: Integrate with motion sensors or cameras to enhance home security.
- **Energy Monitoring**: Track and manage energy consumption via the app.

This project showcases the practical implementation of RISC-V technology by combining microcontroller programming, wireless communication, and IoT concepts to create a smart home solution.

