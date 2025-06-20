# 🔍 License Plate Recognition with YOLO + EasyOCR

This project implements an end-to-end License Plate Recognition (LPR) system using a combination of YOLO (You Only Look Once) for vehicle detection and EasyOCR for optical character recognition of license plates. The system processes input images or frames from a video feed to detect cars, extract license plates, and recognize plate text. It is designed for applications like surveillance, traffic monitoring, and automated vehicle logging.

## 🚀 How it Works

1. **YOLO Detection (Pretrained):**
   - Detects vehicles and their bounding boxes from an image.
   - Crops out the regions where license plates are likely to be.

2. **License Plate Localization:**
   - Applies grayscale conversion, resizing, and noise reduction to prepare for OCR.
   - Uses basic contour filtering to isolate the plate region.

3. **Text Recognition with EasyOCR:**
   - Performs OCR on the extracted plate region.
   - Supports multiple fonts and character sets.

4. **Result Display:**
   - Shows cropped license plate images.
   - Annotates the original image (optional).
   - Displays recognized text with confidence scores.

---

## 🛠️ Technologies Used

- Python
- OpenCV
- EasyOCR
- YOLOv5 (Ultralytics, pretrained)
- Matplotlib
- NumPy

---

## ✅ Features

- Detects multiple vehicles in a frame.
- Crops and processes suspected license plate regions.
- Reads license plate numbers using EasyOCR.
- Displays cropped plate regions for visual verification.
- Handles most frontal or slightly angled license plates.

---

## ⚠️ Limitations

❌ Inconsistent OCR accuracy for:
- Blurry, distant, or low-resolution plates  
- Plates at sharp angles or under poor lighting  
- Plates with non-standard fonts, logos, or symbols  
- Moving vehicles due to motion blur

❌ Misrecognition:
- Confuses similar characters (e.g., O vs 0, I vs 1, B vs 8)

❌ Not optimized for real-time processing or high-speed video feeds.

---

## 📈 Suggestions for Improvement

- Add **super-resolution models** (e.g., Real-ESRGAN) to upscale blurry plates.
- Use **perspective correction** to straighten skewed license plates.
- Replace EasyOCR with **TrOCR** or **CRNN** for better accuracy.
- Incorporate **plate format validation** using regex post-processing.
- Fine-tune YOLO on a custom dataset to better localize plates in your region.

---

## 🧪 Testing

- Tested on sample images of Indian and international license plates.
- Works best with clear, well-lit frontal plate images.

---

## 📂 Dataset

- No training required: used pretrained YOLO and EasyOCR models.
- You can improve performance by collecting real-world images and fine-tuning.

---

## 📌 License

This project is for academic, research, or demo use only. Not intended for real-time enforcement or commercial deployment.

---

# 🚗 License Plate Recognition using YOLOv5 and EasyOCR

This project detects vehicles and extracts license plate numbers from images using deep learning and OCR. It utilizes a **YOLOv5 model trained specifically to detect license plates**, and **EasyOCR** for recognizing plate text.

## 📌 Features
- 🔍 License plate detection using a **YOLOv5-License-Plate model** (trained via Roboflow).
- 🧠 Text extraction from license plates using **EasyOCR**.
- 🖼️ Automatically crops and zooms into license plates from vehicles.
- ⚡ Works on single images or video frames.
- 💬 Displays cropped plate region and recognized text with confidence scores.

## 🧠 Project Architecture

| Step | Tool | Description |
|------|------|-------------|
| 1️⃣ License Plate Detection | YOLOv5 (Roboflow-trained) | Detects and crops plate from image/video |
| 2️⃣ Image Preprocessing | OpenCV | Resizes, enhances, and binarizes cropped plate |
| 3️⃣ Text Recognition | EasyOCR | Extracts license number from plate crop |
| 4️⃣ Output | Matplotlib & Console | Shows plate crop and prints recognized text |


## ✅ Dependencies

- `torch`, `opencv-python`, `matplotlib`
- `easyocr`, `yolov5` from Roboflow (or cloned manually)

## ⚠️ Limitations

❌ **OCR accuracy drops** on blurry, small, or angled license plates.  
❌ Fails on **decorative fonts, small characters, or low contrast** plates.  
❌ Misreads **similar characters** (e.g., `O` vs `0`, `I` vs `1`).  
❌ Not reliable for **real-time fast-moving vehicles**.  
❌ Requires **clear frontal view** of plate for best accuracy.

## 🔧 Improvements To Add

- Use **YOLOv8 or Detectron2** for multi-angle plate detection.
- Add **Super Resolution models (like ESRGAN)** to enhance blurry images.
- Integrate **tracking (e.g., Deep SORT)** for live video feeds.
- Fine-tune OCR with a **custom-trained CRNN model** on license plates.

## 📁 Dataset & Model

- YOLOv5 license plate model was sourced from Roboflow's public project:  
  https://universe.roboflow.com/datasets/license-plate-detection

## 🚀 How To Run

Run the notebook in Google Colab with your own image or video. Upload the image, and it will:
1. Detect the license plate
2. Crop and enhance it
3. Recognize the plate text
4. Show the cropped plate and print the result

---

## 📌 Short Description

Detects vehicles and reads license plates using YOLOv5 and EasyOCR. Handles image/video input and shows cropped plate and recognized text. Best on clear, close-up images.



