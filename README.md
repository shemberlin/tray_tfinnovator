## Google Android phone (arm) Real time detect Result 
---
![image](https://github.com/shemberlin/tray_tfinnovator/blob/3331315961ff6e7c102409392a84e3ddebb1591c/gif/result.gif)
## Nvidia jetson nano Real time detect Result 
![image](https://github.com/shemberlin/tray_tfinnovator/blob/fb9aaae852c774fbe2067c803f81115308349664/gif/real_time_detectation_nvidia_jetson_nano.gif)
## NVIDIA Jetson Nano (ARM Architecture) Real-Time Detection Result with TensorRT
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

## After optimization with TensorRT:
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