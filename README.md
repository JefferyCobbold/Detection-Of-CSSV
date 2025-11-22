Cocoa Swollen Shoot Virus (CSSV) Detection using TinyML

Project Overview

This project implements a real-time, low-cost, and portable diagnostic tool for the early detection of the Cocoa Swollen Shoot Virus (CSSV) using Tiny Machine Learning (TinyML).
By deploying a trained Convolutional Neural Network (CNN) model onto an ESP32-CAM edge device, this system provides cocoa farmers and agricultural personnel with an immediate, on-site assessment of tree infection status.

The goal is to provide a rapid alternative to traditional lab-based testing, facilitating quicker quarantine and removal of infected plants to protect cocoa yields.

Key Features

   Edge Inference: CSSV detection is performed entirely on the ESP32-CAM, requiring no internet connection for prediction.

   Low-Cost Hardware: Utilizes widely available, inexpensive components (ESP32-CAM and OLED display).

   Real-Time Feedback: Inference results and confidence scores are displayed instantly on a small I2C OLED screen.

   Energy Efficient: Designed for low-power operation suitable for in-field, battery-powered use.
