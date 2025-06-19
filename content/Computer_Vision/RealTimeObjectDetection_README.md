Real-time object detection using YOLOv5 in Colab. Detects and tracks objects from webcam snapshots or uploaded video files. Outputs annotated frames with bounding boxes and class labels.


# 🧠 Real-Time Object Detection with YOLOv5

This project performs real-time object detection using YOLOv5 in Google Colab. It supports both webcam snapshots and video file inputs, and outputs annotated frames with bounding boxes and class labels.

## 📌 Features

- 🎥 Real-time webcam snapshot capture in Colab  
- 📼 Object detection on uploaded video files  
- 🧠 Uses pretrained YOLOv5s model  
- 🖼️ Visualizes results with bounding boxes and labels  
- 📦 Downloadable video with detection overlay  

## 🚀 Getting Started

```python
# 1. Clone YOLOv5 and install dependencies
!git clone https://github.com/ultralytics/yolov5
%cd yolov5
%pip install -r requirements.txt

# 2. Load YOLOv5s model
import torch
model = torch.hub.load('ultralytics/yolov5', 'yolov5s', trust_repo=True)

# 3. Capture from webcam (Colab only supports snapshots)
# See notebook for JavaScript+OpenCV integration

# 4. Upload video and process it
from google.colab import files
files.upload()  # Upload your video file

# Process frames, detect objects, and save output_video.mp4

# 5. Convert output for download
!ffmpeg -i output_video.mp4 -vcodec libx264 -acodec aac processed_output.mp4
from google.colab import files
files.download("processed_output.mp4")
```

## 🧪 Output

- `processed_output.mp4`: Final annotated video with detection overlays  
- Recognizes objects from COCO classes (person, car, banana, etc.)

## ✅ Requirements

- Google Colab  
- Python 3.7+  
- PyTorch  
- OpenCV  
- ffmpeg  

## 📎 Notes

- Accuracy may drop with fast motion or poor lighting  
- Hold objects steady and within camera frame for best results  

## 🧠 Credits

- [Ultralytics YOLOv5](https://github.com/ultralytics/yolov5)  
