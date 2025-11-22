# Cocoa Swollen Shoot Virus (CSSV) Detection using TinyML #

### Project Overview ###
This project implements a real-time, low-cost, and portable diagnostic tool for the early detection of the Cocoa Swollen Shoot Virus (CSSV) using Tiny Machine Learning (TinyML).
By deploying a trained Convolutional Neural Network (CNN) model onto an ESP32-CAM edge device, this system provides cocoa farmers and agricultural personnel with an immediate, on-site assessment of tree infection status.

The goal is to provide a rapid alternative to traditional lab-based testing, facilitating quicker quarantine and removal of infected plants to protect cocoa yields.

### Key Features ###

   Edge Inference: CSSV detection is performed entirely on the ESP32-CAM, requiring no internet connection for prediction.

   Low-Cost Hardware: Utilizes widely available, inexpensive components (ESP32-CAM and OLED display).

   Real-Time Feedback: Inference results and confidence scores are displayed instantly on a small I2C OLED screen.

   Energy Efficient: Designed for low-power operation suitable for in-field, battery-powered use.

### Hardware Requirements and Setup

### 1.Hardware Components

| Component        | Description                                     | Quantity |
|------------------|-------------------------------------------------|----------|
| **ESP32-CAM**     | Microcontroller with integrated OV2640 camera     | 1        |
| **OLED Display** | 0.96" I2C (SSD1306) screen for displaying inference results | 1 |
| **FTDI Programmer** | Used for initial flashing and debugging of the ESP32-CAM | 1 |
| **Power Source** | 5V DC supply (e.g., LiPo battery) for portable field deployment | 1 |

### 2. Wiring Diagram
The ESP32-CAM communicates with the OLED display via the I2C protocol.

<img width="720" height="720" alt="CSSV" src="https://github.com/user-attachments/assets/bd709198-ea19-41be-ae61-7ecb48750e09" />

### Software and Dependencies

### 1. Development Environment
 i. Arduino IDE
 
 ii. VS Code
 
 iii. Python 3.10 and Tensorflow for model training

 

## 2.Libraries

| Platform            | Library / Framework                     | Purpose                                      |
|---------------------|-------------------------------------------|----------------------------------------------|
| Arduino / PlatformIO | **esp32-camera**                          | Interface with the camera module             |
| Arduino / PlatformIO | **Adafruit GFX**, **Adafruit SSD1306**    | Control the OLED display                     |
| Python              | **TensorFlow / Keras**                    | Model training and development               |
| Python              | **TensorFlow Lite Micro**                 | Model quantization and deployment tools      |






