Google Android phone (arm) Real time detect Result 
---
![image](https://github.com/shemberlin/tray_tfinnovator/blob/3331315961ff6e7c102409392a84e3ddebb1591c/gif/result.gif)
Nvidia jetson nano Real time detect Result 
![image](https://github.com/shemberlin/tray_tfinnovator/blob/fb9aaae852c774fbe2067c803f81115308349664/gif/real_time_detectation_nvidia_jetson_nano.gif)
Nvidia jetson nano (arm) Real time detect Result Tersorrt
![image](https://github.com/shemberlin/tray_tfinnovator/blob/3331315961ff6e7c102409392a84e3ddebb1591c/gif/real_time_detectation_nvidia_jetson_nano_tensorrt.gif)

---
## Ultra High level process for deploying AI solutions (Hybrid solution) Not end to end
![image](https://github.com/shemberlin/tray_tfinnovator/blob/961e97bafc864278c83792271f03c61601eac4b1/gif/ultra_high_level_process_for_deploying_AI_solution.gif)

## Discription
This flowchart outlines the AI model development and deployment process. 

First, images are taken and annotated with LabelImg. 

The dataset is uploaded to Google Colab for training with the YOLOv5 model.

After the model training, it is deployed separately to a smart phone and an edge device - Jetson Nano, with TensorRT used for optimization. 
## Technical explain

### Data Collection and Annotation
*	Capture image data using a camera as training samples.
*	Use LabelImg as an annotation tool to label images and generate datasets containing train (training data) and val (validation data).

2. Model Training
*	Upload data to Google Colab, leveraging cloud computing resources for model training.
*	Use PyTorch as the deep learning framework and choose Ultralytics YOLOv5 as the base object detection model.

3. Model Conversion and Optimization
*	After training, convert the YOLOv5 model into ONNX format, an open neural network exchange format that enables cross-platform deployment.
*	Use TensorRT for model optimization, enhancing inference speed and reducing latency.

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


## NVIDIA Jetson Nano full image file
https://drive.google.com/file/d/1YikbwvXPR4rfkoOafR4yyNZYi4hsaJj0/view?usp=sharing
## Usage
### 1. Git clone Ultralytics `yolov5`
```
git clone https://github.com/ultralytics/yolov5.git
cd yolov5
```

### 2. Convert and verify
- Convert weights to fp16 TFLite model, and verify it with
```
python export.py --weights yolov5s.pt --include tflite --img 320
python detect.py --weights yolov5s-fp16.tflite --img 320
```
or 
- Convert weights to int8 TFLite model, and verify it with
```
python export.py --weights yolov5s.pt --include tflite --int8 --img 320 --data data/coco128.yaml
python detect.py --weights yolov5s-int8.tflite --img 320
```
Note that:
* int8 quantization needs dataset images to calibrate weights and activations, and the default COCO128 dataset is downloaded automatically.
* Change `--img` to the input resolution of your model, if it isn't 320. 

### 3. Clone this repo (tf-android branch) for Android app
```
git clone https://github.com/zldrobit/yolov5.git yolov5-android
```

### 4. Put TFLite models in `assets` folder of Android project, and change 
- `inputSize` to `--img`
- `output_width` according to new/old `inputSize` ratio
- `anchors` to `m.anchor_grid` as https://github.com/ultralytics/yolov5/pull/1127#issuecomment-714651073 
in android/app/src/main/java/org/tensorflow/lite/examples/detection/tflite/DetectorFactory.java
- `labelFilename` according to the classes of the model
in https://github.com/zldrobit/yolov5/blob/522d65e848d3e5a378eb0f29a9fbb204221400e8/android/app/src/main/java/org/tensorflow/lite/examples/detection/tflite/DetectorFactory.java#L19-L48. 

Then run the program in Android Studio.

TODO:
- [ ] Add NNAPI support

EDIT: 
- Update according YOLOv5 v6.0 release

If you have further question, plz ask in https://github.com/ultralytics/yolov5/pull/1127

## Reference:
https://github.com/hunglc007/tensorflow-yolov4-tflite.git
