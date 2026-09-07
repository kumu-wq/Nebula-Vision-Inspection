# Nebula AI Vision Inspection

An AI-assisted computer vision prototype for automated inspection and dimensional measurement of mechanical components.

## Project Overview

This project demonstrates a vision-based inspection workflow for mechanical components such as bolts, nuts, washers, and plates.

The system uses a camera image to detect the component, estimate its dimensions using calibration, perform a basic defect check, determine PASS/FAIL based on tolerance, and generate an inspection report in PDF format.

## Features

* 📷 Camera-based component image capture
* 🔍 Automatic object detection using OpenCV.js
* 📏 Automatic dimensional measurement
* ⚙️ Manual pixel-to-millimeter calibration
* 🔩 Support for Bolt, Nut, Washer, and Plate components
* 🟢 PASS/FAIL inspection based on expected dimension and tolerance
* 🔎 Basic defect inspection for nuts and washers
* ⚙️ Washer outer and inner diameter measurement
* 📄 PDF inspection report generation
* 🖼️ Captured component image included in the PDF report
* 🌐 Browser-based user interface

## Technologies Used

* Python
* FastAPI
* HTML
* CSS
* JavaScript
* OpenCV.js
* jsPDF
* Web Camera API

## Project Structure

```text
Nebula_Vision_Inspection/
│
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
│
├── templates/
│   └── index.html
│
└── static/
    ├── style.css
    └── script.js
```

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/kumu-wq/Nebula-Vision-Inspection.git
cd Nebula-Vision-Inspection
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Start the FastAPI Server

```bash
python -m uvicorn app:app --reload
```

### 4. Open the Application

Open the following address in a browser:

```text
http://127.0.0.1:8000
```

Allow camera access when requested.

## Inspection Workflow

```text
Camera
   ↓
Capture Component
   ↓
Calibration
   ↓
OpenCV Image Processing
   ↓
Object Detection
   ↓
Dimensional Measurement
   ↓
Defect Check
   ↓
PASS / FAIL
   ↓
PDF Inspection Report
```

## Calibration

The system uses a known reference dimension to convert pixels into millimeters.

The calibration is calculated using:

```text
Pixels per MM = Reference Pixels / Reference Dimension (MM)
```

The detected component dimension is then converted from pixels to millimeters.

Accurate calibration and a suitable camera setup are important for reliable measurements.

## PASS / FAIL Inspection

The measured dimension is compared with the expected dimension and tolerance.

```text
Lower Limit = Expected Dimension - Tolerance

Upper Limit = Expected Dimension + Tolerance
```

If the measured dimension falls within the acceptable range, the component is classified as:

```text
PASS
```

Otherwise:

```text
FAIL
```

## Defect Inspection

For nuts and washers, the prototype performs a basic internal-hole inspection using OpenCV contour analysis.

The system checks whether an internal hole is detected and reports a possible missing-hole defect when no suitable hole is detected.

This is a basic prototype inspection and is not intended to replace industrial-grade defect detection systems.

## PDF Inspection Report

The application can generate a PDF report containing:

* Component type
* Measured dimension
* Expected dimension
* Tolerance
* Defect inspection result
* PASS/FAIL result
* Inspection reason
* Inspection date and time
* Captured component image

## Limitations

This prototype is intended for demonstration and proof-of-concept purposes.

Measurement accuracy can be affected by:

* Camera position
* Lighting conditions
* Object orientation
* Background contrast
* Calibration accuracy
* Image resolution

The current defect inspection is a basic computer-vision check and does not use a trained deep-learning defect classification model.

## Future Improvements

Possible future improvements include:

* YOLO-based component detection
* Deep-learning-based defect classification
* Automatic reference calibration
* Multiple-camera inspection
* Improved lighting control
* Perspective correction
* Industrial camera integration
* Database storage of inspection results
* Real-time production-line integration

## Author

**Kumutha O**

Robotics and Automation Engineering

## Project Purpose

Developed as a prototype for an AI vision-based mechanical component inspection and measurement system.
