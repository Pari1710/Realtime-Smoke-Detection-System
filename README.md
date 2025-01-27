
# **Smoke Detection System with IoT Integration**

## **Overview**
This project implements a Smoke Detection System using an ESP8266 microcontroller, a gas sensor, a buzzer, and an OLED display. It integrates with the **Blynk platform** for real-time monitoring of gas levels and sends alerts when dangerous levels are detected.

## **Features**
- Real-time monitoring of gas levels using a gas sensor.
- Displays gas values and system status (Normal/High Alert) on an OLED screen.
- Sound alert through a buzzer when high gas levels are detected.
- IoT integration with Blynk for real-time monitoring and control.
- Manual buzzer control via the Blynk app.

---

## **Components Required**
1. **ESP8266** (NodeMCU or similar): Microcontroller for WiFi connectivity.
2. **MQ Gas Sensor** (or equivalent): To detect gas concentrations.
3. **Buzzer**: Provides sound alert when gas levels exceed the threshold.
4. **OLED Display (SSD1306)**: Displays the gas levels and system status.
5. **Jumper Wires**: For connecting components.
6. **Breadboard**: For prototyping the circuit.

---

## **Software Libraries Used**
1. **Blynk**: For IoT integration and app interface.
2. **Adafruit SSD1306**: To control the OLED display.
3. **Adafruit GFX**: For OLED graphics handling.
4. **ESP8266WiFi**: For WiFi connectivity.

---

## **Project Setup**

### **Hardware Connections**
1. **Gas Sensor (MQ Sensor)**  
   - Connect the analog output (A0) pin of the gas sensor to the A0 pin on the ESP8266.
2. **Buzzer**  
   - Connect the buzzer to the D6 pin on the ESP8266.
3. **OLED Display**  
   - Connect the OLED display to the I2C pins (SCL and SDA) of the ESP8266.

### **Software Setup**
1. **Install Libraries**
   Ensure the following libraries are installed in your Arduino IDE:
   - Blynk
   - Adafruit SSD1306
   - Adafruit GFX
   - ESP8266WiFi

2. **Blynk Setup**
   - Create a project in the Blynk app on your smartphone.
   - Set up a button on Virtual Pin V1 to control the buzzer manually.
   - Use the provided **Auth Token** in the code to authenticate with the Blynk app.

3. **WiFi Setup**
   - Enter your WiFi credentials in the `ssid[]` and `pass[]` variables in the code.

4. **Threshold Adjustment**
   - Adjust the gas detection threshold in the `sensorThreshold` variable based on your sensor's sensitivity.

---

## **Code Features**
### **Initialization**
- **WiFi Connectivity:** The ESP8266 connects to your WiFi network using the credentials provided.
- **OLED Display:** Displays real-time gas values and system status.
- **Buzzer:** Sounds an alert for 3 seconds if gas levels exceed the threshold.

### **Blynk Integration**
- **Virtual Pin V1:** Allows manual buzzer control via the Blynk app.

### **Gas Detection**
- Continuously reads the gas sensor values.
- Compares the values to the predefined threshold.
- Displays "High Alert" on the OLED and triggers the buzzer if the threshold is exceeded; otherwise, displays "Normal."

### **Buzzer Control**
- Automatically stops after 3 seconds or can be manually stopped from the Blynk app.

---

## **Troubleshooting**
- **OLED not displaying:** Ensure correct I2C connections and use the correct address (default: `0x3C`).
- **Gas Sensor issues:** Calibrate the sensor or adjust the threshold as needed.
- **Blynk app not connecting:** Verify the Auth Token and WiFi credentials.

---

## **Future Improvements**
1. **Push Notifications:** Integrate with IFTTT for mobile or email alerts.
2. **Multiple Sensors:** Add smoke or temperature sensors for enhanced functionality.
3. **Web Dashboard:** Develop a web interface for remote monitoring.

---

## **License**
This project is open-source. Feel free to modify and contribute.  
**Let’s make IoT smarter and safer!**
