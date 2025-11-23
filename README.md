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



### Model Training and TinyML Implementation
### 1. Dataset
The model was trained on an open-source dataset of cocoa leaf images categorized into 'Healthy' and 'CSSV Infected' classes.

### 2. Training Performance
The model training process utilized Transfer Learning (or a custom CNN architecture) and was rigorously monitored to ensure optimal performance on unseen validation data.

Accuracy: The final validation accuracy reached 98% after 20 epochs, demonstrating high classification reliability.
<img width="720" height="622" alt="Accuracy Curve" src="https://github.com/user-attachments/assets/385c3c91-6891-4751-8c7d-9e440c74fdbb" />


<img width="720" height="622" alt="Loss Curve" src="https://github.com/user-attachments/assets/7a77d156-faaf-4906-a99a-6bab241ad255" />

Optimization: The trained model was converted to a TensorFlow Lite format and then quantized to 8-bit integers to drastically reduce the model size (to under 300KB) and inference time, making it suitable for the ESP32's limited resources.


### 3. Inference Cycle
1.Capture: The ESP32-CAM captures an image of the cocoa leaf.

2.Pre-processing: The image is resized and converted into a format suitable for the TinyML model (e.g., a $96 \times 96$ grayscale array).

3.Inference: The quantized CNN model runs the prediction on the processed image data.

4.Display: The result is immediately displayed on the OLED screen, showing the class (CSSV    Detected or Healthy) and the prediction confidence.






