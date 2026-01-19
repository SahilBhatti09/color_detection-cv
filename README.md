# 🎯 Color-Based Object Detection System

A beginner-friendly real-time color detection project using OpenCV that detects and tracks colored objects through your webcam.

---

## 🎬 Overview

This project demonstrates **computer vision fundamentals** by detecting colored objects in real-time using your webcam. It uses **HSV color space** and **contour detection** to identify and track objects by their color, drawing labeled bounding boxes around each detected item.


---

## ✨ Features

### Core Functionality
- ✅ **Real-time object detection** using webcam
- ✅ **Multi-color tracking** (Red, Blue, Green, Yellow)
- ✅ **Automatic labeling** with color name and object size
- ✅ **Live statistics** showing object counts by color
- ✅ **Frame capture** - save detected frames with 's' key
- ✅ **Clean interface** with semi-transparent info overlay

### Technical Highlights
- 🎨 **HSV color space** conversion for robust detection
- 🔍 **Morphological operations** for noise reduction
- 📐 **Contour detection** for object boundary finding
- 📊 **Bounding rectangles** with center point marking
- 🎯 **Area-based filtering** to ignore small noise

---

## 🖼️ Demo

### Sample Detections

The project successfully detected multiple colored objects:

- **Red objects**: table, markers
- **Blue objects**: Notebooks, shirt
- **Green objects**: seprations, ring stone

### Output Features
- Colored bounding boxes around each object
- Labels showing "COLOR Object" and area in pixels
- Yellow center point marking
- Top info panel with total counts
- Real-time statistics display

---

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- Webcam (built-in or external)
- macOS, Windows, or Linux

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/color-detection-opencv.git
cd color-detection-opencv
```

### Step 2: Create Virtual Environment

```bash
# Create virtual environment
python3 -m venv venv

# Activate virtual environment
# On macOS/Linux:
source venv/bin/activate

# On Windows:
venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install opencv-python numpy jupyter
```

Or use the requirements file:

```bash
pip install -r requirements.txt
```

### Step 4: Launch Jupyter Notebook

```bash
jupyter notebook color_detect.ipynb
```

---

## 🎮 Usage

### Quick Start

1. **Open the notebook**: Launch `color_detect.ipynb` in Jupyter
2. **Run setup cells**: Execute cells 1-4 to import libraries and define colors
3. **Start detection**: Run cell 5 to open webcam and start detection
4. **Test with objects**: Hold colored items in front of camera

### Controls

| Key | Action |
|-----|--------|
| `q` | Quit the program |
| `s` | Save current frame |
| `ESC` | Alternative quit method |

### Tips for Best Results

- 📷 **Good lighting**: Ensure adequate, even lighting
- 🎨 **Solid colors**: Use objects with vivid, uniform colors
- 🖼️ **Plain background**: White wall or plain surface works best
- 📏 **Object size**: Objects should be at least 500 pixels in area
- 🔆 **Avoid glare**: Position objects to minimize reflections

---

## 🔧 How It Works

### Detection Pipeline

```
1. 📹 Capture Frame from Webcam
   ↓
2. 🎨 Convert BGR → HSV Color Space
   ↓
3. 🎭 Create Binary Mask (Color Filtering)
   ↓
4. 🧹 Apply Morphological Operations
   │   ├── Erosion (Remove Noise)
   │   └── Dilation (Fill Gaps)
   ↓
5. 📐 Find Contours (Object Boundaries)
   ↓
6. 📊 Filter by Area (Remove Small Noise)
   ↓
7. 🖍️ Draw Bounding Rectangles
   ↓
8. 🏷️ Add Labels & Information
   ↓
9. 📺 Display Result
   ↓
10. 🔄 Repeat (30 FPS)
```

---

## 🧪 Technical Details

### HSV Color Ranges

The project uses these HSV ranges for detection:

| Color | Hue Range | Saturation | Value | Notes |
|-------|-----------|------------|-------|-------|
| **Red** | 0-10, 160-180 | 100-255 | 100-255 | Wraps around HSV |
| **Blue** | 100-130 | 100-255 | 100-255 | Standard range |
| **Green** | 40-80 | 50-255 | 50-255 | Includes lime |
| **Yellow** | 20-40 | 100-255 | 100-255 | Bright yellows |

### OpenCV Functions Used

1. **`cv2.VideoCapture()`** - Camera access
2. **`cv2.cvtColor()`** - Color space conversion
3. **`cv2.inRange()`** - Color masking
4. **`cv2.erode()`** - Morphological erosion
5. **`cv2.dilate()`** - Morphological dilation
6. **`cv2.findContours()`** - Contour detection
7. **`cv2.contourArea()`** - Area calculation
8. **`cv2.boundingRect()`** - Bounding box coordinates
9. **`cv2.rectangle()`** - Drawing rectangles
10. **`cv2.putText()`** - Adding text labels
11. **`cv2.circle()`** - Drawing center points
12. **`cv2.addWeighted()`** - Blending images
13. **`cv2.bitwise_or()`** - Mask combination

---

## 🔮 Future Improvements

### Easy Enhancements
- [ ] Add more colors (orange, purple, pink, white, black)
- [ ] Add sound alerts when objects detected
- [ ] Save detection video (not just frames)
- [ ] Add timestamp to saved images
- [ ] Shape detection (circle, square, triangle identification)
- [ ] Web-based interface using Flask/Django

---

## 📁 Project Structure

```
opencv/
├── color_detect.ipynb          # Main notebook with detection code
├── README.md                   # This file
├── requirements.txt            # Python dependencies
├── detected_objects_0.jpg      # Saved detection frames
├── detected_objects_1.jpg
├── detected_objects_2.jpg
├── detected_objects_3.jpg
└── etected_objects_4.jpg
```

---


## 👨‍💻 Author
 
Sahil Bhatti
