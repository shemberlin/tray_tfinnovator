


## Samsung S20 Ultra 5G with Google Android System - Real-Time Detection Results
---
![image](https://github.com/shemberlin/tray_tfinnovator/blob/3331315961ff6e7c102409392a84e3ddebb1591c/gif/result.gif)
### What is tray?
The term “Tray” generally refers to a flat container or platform used for holding, organizing, or transporting items. 
Its meaning depends on the specific context:
1. Industrial & Electronics
*	IC Tray (Integrated Circuit Tray): Used for storing and transporting electronic components, especially in SMT (Surface Mount Technology) production lines.
2. Computers & Operating Systems
*	In Windows or macOS, the “System Tray” (also known as the notification area) is the section of the taskbar that displays icons for system status, background applications, Wi-Fi, volume control, battery status, etc.
*	Some applications minimize to the system tray, allowing them to run in the background without occupying the main screen.
*	HDD Tray (Hard Drive Tray): A removable or fixed bracket for holding hard drives, commonly found in server racks or external hard drive enclosures.
3. Machinery & Automation
*	Robotic Tray: In automated production lines, robotic arms pick and place objects from a tray, assisting in assembly or transportation.
4. Food & Daily Life
*	Food Tray: A flat serving tray used in restaurants, cafeterias, or catering services.
*	Ice Tray: A plastic or silicone mold used for making ice cubes.
### Explanation of Each Screen:
1. First Image (Leftmost) - “About Phone” Information
*	Displays basic device information, including Model (SM-G9880), Product Name (Galaxy S20 Ultra 5G), IMEI numbers, etc.
*	This is likely used to confirm the exact specifications of the device, ensuring the testing environment matches the required conditions.
2. Second Image (Second from Left) - “Software Information”
*	Shows details such as One UI version (5.1), Android version (13), Baseband version, Kernel version (4.19.113), and Knox security version.
*	These details help developers verify firmware, OS compatibility, and security features, which are crucial when testing AI models or app compatibility.
3. Third Image (Second from Right) - TensorFlow Lite AI Object Detection
*	This screen displays an AI object detection application running TensorFlow Lite, possibly using the YOLOv5 object detection model (YOLOv5s-fp16.tflite).
*	The “OK 87.84%” labels indicate the model’s confidence scores in detecting objects within the image (likely objects inside a tray).
*	This type of testing is commonly used in edge AI inference, where AI models run on a mobile device instead of relying on cloud computing.
4. Fourth Image (Rightmost) - CPU-Z Hardware Information
*	This screen shows the CPU-Z application, providing details about the device’s processor:
*	Processor Model: Qualcomm Snapdragon 865
*	Clock Speed: 300 MHz - 2.84 GHz
*	Core Architecture: big.LITTLE, Kryo 585
*	Process Technology: 7nm
*	GPU Model: Adreno 650

## Nvidia jetson nano Real time detect Result 
![image](https://github.com/shemberlin/tray_tfinnovator/blob/fb9aaae852c774fbe2067c803f81115308349664/gif/real_time_detectation_nvidia_jetson_nano.gif)
## NVIDIA Jetson Nano Real-Time Detection Result with TensorRT
![image](https://github.com/shemberlin/tray_tfinnovator/blob/3331315961ff6e7c102409392a84e3ddebb1591c/gif/real_time_detectation_nvidia_jetson_nano_tensorrt.gif)
## Breakdown of the Content:
1. Title: “Real-time detection” — emphasizing the ability to detect objects in real-time.
2.	Key Technology: “TensorRT engine => inference time Faster 59%” — TensorRT enhances inference speed, improving overall performance by 59%.
3.	Performance Comparison:
*	Before Optimization (Left Image):
*	Inference Time: ~54ms
*	Frame Rate (FPS): 18fps
*	After Optimization (Right Image) (using TensorRT):
*	Inference Time: ~34ms
*	Frame Rate (FPS): 29fps
4.	Visualized Results:
*	Both screenshots display object detection results, where red bounding boxes highlight detected objects with confidence scores (e.g., 0.90, 0.88, etc.).
*	The label “OK” in the detection results likely indicates that the detected objects meet certain criteria or pass the inspection.

## Conclusion:
###  After optimization with TensorRT:
*	Inference time is reduced (from 54ms to 34ms).
*	Frame rate increases (from 18fps to 29fps).
*	Achieves a 59% performance boost, making real-time detection significantly faster and smoother.

*	This kind of performance enhancement is crucial for applications requiring high-efficiency inference, such as edge AI, machine vision, and automated inspection systems.
---
## Ultra High level process for deploying AI solutions (Multi solution) 
![image](https://github.com/shemberlin/tray_tfinnovator/blob/961e97bafc864278c83792271f03c61601eac4b1/gif/ultra_high_level_process_for_deploying_AI_solution.gif)

## Discription
*	Not end to end solution.

*	This flowchart outlines the AI model development and deployment process. 

*	First, images are taken and annotated with LabelImg. 

*	The dataset is uploaded to Google Colab for training with the YOLOv5 model.

*	After the model training, it is deployed separately to a smart phone and an edge device - Jetson Nano, with TensorRT used for optimization. 
## Technical explain

1. Data Collection and Annotation
*	Capture image data using an iPad Pro camera as training samples.
*	Use LabelImg as an annotation tool to label images and generate datasets containing train (training data) and val (validation data).

2. Model Training
*	Upload data to Google Colab, leveraging cloud computing resources for model training.
*	Use PyTorch as the deep learning framework and choose Ultralytics YOLOv5 as the base object detection model.

3. Model Conversion and Optimization
*	After training, convert the YOLOv5 model from h5 format into ONNX format, an open neural network exchange format that enables cross-platform deployment.
*	Use TensorRT for model optimization, enhancing inference speed, reducing latency, and significantly increasing FPS.

4. Deployment to Different Devices
*	Mobile Device Deployment:
*	Convert the model to TensorFlow Lite (TFLite) to suit mobile environments.
*	Deploy to Samsung S20 Ultra 5G for real-time object detection in real-world scenarios.
*	Edge Device Deployment:
*	Further optimize the model using TensorRT, generating an efficient inference engine.
*	Deploy to Nvidia Jetson Nano, utilizing edge computing for real-time object detection locally.

5. Final Application
*	Both mobile and edge devices can perform real-time object detection and output test data for real-world validation and application.

Technical Highlights
*	Cloud Training (Google Colab) reduces local computation burden, providing a flexible and efficient training environment.
*	Android development benefits from cloud-based training by offloading intensive computations, reducing the processing load on mobile devices.
*	Cloud-based training enables real-time AI model updates, ensuring up-to-date performance and improved efficiency on Android platforms.

## NVIDIA Jetson Nano full image file
https://drive.google.com/file/d/1YikbwvXPR4rfkoOafR4yyNZYi4hsaJj0/view?usp=sharing