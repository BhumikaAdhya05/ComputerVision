**Short Description:**  
Detects and extracts license plate numbers from vehicle images using Tesseract OCR and contour detection. Includes preprocessing steps, but OCR accuracy is inconsistent across image types.

---

# License Plate Recognition using Tesseract OCR

This project detects and extracts license plate numbers from vehicle images using classical computer vision techniques and Tesseract OCR.

## 🚀 Features

- Detects license plate from full car image using contour detection.
- Applies image preprocessing: edge detection, filtering, thresholding.
- Extracts alphanumeric license text using Tesseract OCR.
- Works with `.jpg`, `.png`, and uploaded images in Google Colab.
- Plots the detected plate image and prints the extracted number.

## 🛠️ Requirements

- Python
- OpenCV
- Tesseract-OCR
- Matplotlib
- pytesseract
- Google Colab (for easy file uploads)

Install required packages:

```bash
!pip install pytesseract opencv-python-headless matplotlib
!apt install tesseract-ocr
```

## 📂 How it works

1. **Load and preprocess the image**  
   - Convert image to grayscale.  
   - Apply bilateral filtering to remove noise while preserving edges.  
   - Use Canny edge detection to highlight edges.

2. **Detect contours and find license plate region**  
   - Identify contours in the edged image.  
   - Approximate each contour to a polygon.  
   - Select the contour with four sides (likely a license plate).  
   - Extract (crop) the plate region from the image.

3. **Enhance cropped plate for OCR**  
   - Resize the cropped region to enlarge text.  
   - Apply Gaussian blur and adaptive thresholding to clean up the image.

4. **Apply Tesseract OCR**  
   - Use `pytesseract.image_to_string()` to extract text.  
   - Tune `--psm` (Page Segmentation Mode) for better results (e.g., `psm 6` or `8`).  
   - Filter the output to keep only alphanumeric characters.

5. **Display the final result**  
   - Show the detected plate image.  
   - Print the extracted license plate number.

---

## ⚠️ Limitations

❌ Inconsistent OCR accuracy on blurry, angled, or poorly lit images.  
❌ Fails when license plates have state logos, fancy fonts, or small characters.  
❌ Misreads common characters (O vs 0, I vs 1, etc.).  
❌ Not suitable for real-time or highly reliable applications.
