# Live Face Recognition - Setup Guide
# ===================================

## Quick Start

### 1. Install Python (if not already installed)
- Download Python 3.8+ from https://python.org
- Make sure to check "Add Python to PATH" during installation

### 2. Install Dependencies
```powershell
# Navigate to the Components directory
cd "c:\Users\skrishna\OneDrive - Nokia\Code\Components"

# Install required packages
pip install -r requirements.txt

# Alternative: Install packages individually
pip install opencv-python face-recognition numpy Pillow
```

### 3. Prepare a Reference Image
- Take a clear photo of the person's face (JPEG/PNG format)
- Save it in the Components directory (e.g., "reference_face.jpg")
- The image should have:
  - Clear, well-lit face
  - Person looking at camera
  - Minimal background noise
  - Only one person in the image

### 4. Run the Script

#### Method 1: Command Line with Image Path
```powershell
python live_face_recognition.py "reference_face.jpg"
```

#### Method 2: Interactive Mode
```powershell
python live_face_recognition.py
# Then enter the image path when prompted
```

### 5. Usage Instructions
- Position your face clearly in front of the camera
- The system will automatically check your face every 2 seconds
- Press 'q' to quit
- Press 'space' for manual verification
- Green box = Face matched
- Red box = Face not matched
- Yellow box = Checking in progress

## Troubleshooting

### Camera Issues
- Make sure no other applications are using the camera
- Try unplugging and reconnecting USB cameras
- Check camera permissions in Windows settings

### Installation Issues
- If `face-recognition` fails to install:
  ```powershell
  pip install cmake
  pip install dlib
  pip install face-recognition
  ```

### Performance Issues
- Lower camera resolution by modifying the script
- Increase check interval (change check_interval value)
- Close other applications using CPU/camera

## Example Usage

```powershell
# Basic usage
python live_face_recognition.py "my_photo.jpg"

# With custom confidence threshold (0.0-1.0)
# Run script and enter 0.8 when prompted for threshold
```

## Configuration Options

You can modify these values in the script:
- `confidence_threshold`: Minimum match confidence (default: 0.6)
- `check_interval`: Time between automatic checks in seconds (default: 2.0)
- Camera resolution: Modify CAP_PROP_FRAME_WIDTH and CAP_PROP_FRAME_HEIGHT

## File Requirements
- Python script: `live_face_recognition.py`
- Dependencies: `requirements.txt`
- Reference image: Any JPEG/PNG with a clear face

## System Requirements
- Python 3.8 or higher
- Webcam or USB camera
- Windows 10/11 (or Linux/macOS with minor modifications)
- At least 4GB RAM recommended
