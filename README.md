
# OpenCV – Computer Vision 
## Introduction
- OpenCV (Open Source Computer Vision Library) is an open-source computer vision and machine learning software library.
- It provides tools to process images and videos, enabling tasks like object detection, image enhancement, and real-time vision applications.

### 🛠️ Installation
- Install OpenCV using pip: pip install opencv-python

- For extra features (like non-free algorithms): pip install opencv-contrib-python

### 📂 Basic Operations
1. Reading and Displaying Images
2. Video Capture
   
### 🎨 Image Processing Techniques
1. Arithmetic Operations
- Addition → Brightness increase
- Subtraction → Darkening
- Multiplication → Contrast enhancement
- Division → Normalization
2. Filtering
- Blurring → Noise reduction
- Sharpening → Highlight details
- Edge Detection → Sobel, Canny
3. Morphological Operations
- Erosion → Removes noise
- Dilation → Fills gaps
- Opening → Noise removal
- Closing → Hole filling
- Gradient → Boundary extraction
4. Thresholding
- Binary Thresholding → Convert grayscale to black & white
- Adaptive Thresholding → Handles uneven lighting
- Otsu’s Method → Automatic threshold selection

### 📐 Contours
Contours are curves joining continuous points along boundaries.
contours, hierarchy = cv2.findContours(thresh, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)
cv2.drawContours(img, contours, -1, (0,255,0), 2)

### 🔄 Image Alignment
Aligns one image with another using feature matching (ORB, SIFT, SURF) and homography.
👉 Useful in medical imaging, panorama stitching, and AR.

### Panorama (Image Stitching)
Combine overlapping images into a wide-angle view.
stitcher = cv2.Stitcher_create()
(status, pano) = stitcher.stitch([img1, img2])

## Visual Workflow Diagram
Here’s a simple ASCII-style flowchart to show the OpenCV pipeline:
  

┌────────────────────────────────────────────────────────────────────────────┐
│                               Computer Vision Flow                         │
└────────────────────────────────────────────────────────────────────────────┘

Input
  ┌─────────────────────────┐
  │ Image(s) / Video stream │
  └──────────────┬──────────┘
                 │
                 ▼
Preprocessing
  ┌───────────────────────────────────────────────────────────┐
  │ Resize • Color convert (BGR→Gray) • Denoise (Blur/Median) │
  │ Normalize • Crop/ROI • Gamma/Histogram adjustments        │
  └──────────────┬────────────────────────────────────────────┘
                 │
                 ▼
Core image processing
  ┌───────────────────────────────────────────────────────────┐
  │ Arithmetic (add/subtract/multiply)                        │
  │ Filtering (blur/sharpen/edge detect: Sobel, Canny)        │
  │ Morphology (erode/dilate/open/close/gradient)             │
  │ Thresholding (global/adaptive/Otsu)                       │
  └──────────────┬────────────────────────────────────────────┘
                 │
                 ▼
Feature extraction
  ┌───────────────────────────────────────────────────────────┐
  │ Contours • Keypoints (ORB/SIFT/SURF) • Descriptors        │
  │ Corners (Harris) • Lines (Hough) • Regions (MSER)         │
  └──────────────┬────────────────────────────────────────────┘
                 │
                 ▼
Geometry & alignment
  ┌───────────────────────────────────────────────────────────┐
  │ Feature matching • Homography • Warp/Affine/Perspective   │
  │ Registration • Panorama stitching                         │
  └──────────────┬────────────────────────────────────────────┘
                 │
                 ▼
Analysis & decisions
  ┌───────────────────────────────────────────────────────────┐
  │ Measurements (area, perimeter, centroid)                  │
  │ Detection/Tracking • Classification (ML/DL)               │
  │ OCR • Quality checks • Event triggers                     │
  └──────────────┬────────────────────────────────────────────┘
                 │
                 ▼
Output
  ┌───────────────────────────────────────────────────────────┐
  │ Visual overlays • Saved images/videos • Metrics/Reports   │
  │ Real-time UI dashboards • API responses                   │
  └───────────────────────────────────────────────────────────┘


### Applications of OpenCV
- Object detection and tracking
- Face recognition
- OCR (text recognition)
- Augmented reality
- Industrial inspection
- Medical imaging


