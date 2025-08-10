# Hand Volume Control Using Python

A real-time hand gesture-based volume control system that uses computer vision to detect hand landmarks and control system volume through finger distance measurement.

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green.svg)
![MediaPipe](https://img.shields.io/badge/MediaPipe-latest-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 🎯 Features

- **Real-time Hand Detection**: Uses MediaPipe for accurate hand landmark detection
- **Gesture-based Volume Control**: Controls system volume by measuring distance between thumb and index finger
- **Visual Feedback**: Live camera feed with hand landmarks and connection lines
- **Cross-platform**: Works on Windows, macOS, and Linux
- **Adjustable Window**: Resizable display window for better visibility
- **Simple Controls**: ESC key to exit the application

## 🛠️ Requirements

### System Requirements
- Python 3.7 or higher
- Webcam/Camera access
- Operating System: Windows 10+, macOS 10.14+, or Linux

### Python Dependencies
```txt
opencv-python>=4.5.0
mediapipe>=0.8.0
pyautogui>=0.9.50
```

## 📦 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/hand-volume-control.git
   cd hand-volume-control
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

   Or install individually:
   ```bash
   pip install opencv-python mediapipe pyautogui
   ```

## 🚀 Usage

1. **Run the application**
   ```bash
   python hand_volume_control.py
   ```

2. **Control Volume**
   - **Volume Up**: Spread your thumb and index finger apart (distance > 20 pixels)
   - **Volume Down**: Bring your thumb and index finger close together (distance ≤ 20 pixels)

3. **Exit**
   - Press `ESC` key to quit the application

## 🎮 How It Works

### Hand Detection
The application uses MediaPipe's hand detection model to identify 21 hand landmarks in real-time from the webcam feed.

### Key Landmarks Used
- **Landmark 4**: Thumb tip
- **Landmark 8**: Index finger tip

### Volume Control Logic
```python
# Calculate distance between thumb and index finger
distance = sqrt((x2-x1)² + (y2-y1)²) / 4

# Control volume based on distance
if distance > 20:
    pyautogui.press("volumeup")
else:
    pyautogui.press("volumedown")
```

## 🔧 Configuration

### Adjust Sensitivity
Modify the distance threshold in the code:
```python
if dist > 20:  # Change this value to adjust sensitivity
    pyautogui.press("volumeup")
```

### Window Size
Change the display window dimensions:
```python
cv2.resizeWindow("Hand volume control using python", 800, 600)  # width, height
```

### Camera Selection
Use a different camera by changing the camera index:
```python
webcam = cv2.VideoCapture(1)  # 0 = default camera, 1 = external camera
```

## 📁 Project Structure

```
hand-volume-control/
│
├── hand_volume_control.py    # Main application file
├── requirements.txt          # Python dependencies
├── README.md                # Project documentation
└── assets/                  # Images and demos (optional)
    ├── demo.gif
    └── screenshot.png
```

## 🐛 Troubleshooting

### Common Issues

1. **Camera not detected**
   - Ensure your webcam is properly connected
   - Check if other applications are using the camera
   - Try changing the camera index: `cv2.VideoCapture(1)`

2. **ModuleNotFoundError**
   ```bash
   pip install --upgrade opencv-python mediapipe pyautogui
   ```

3. **Permission denied (macOS)**
   - Go to System Preferences > Security & Privacy > Privacy
   - Enable camera access for Terminal/Python

4. **Volume keys not working**
   - Ensure your system supports volume key simulation
   - On Linux, you might need to install additional packages

### Performance Issues
- Close other camera-using applications
- Ensure good lighting conditions
- Keep your hand within the camera frame
- Maintain reasonable distance from camera (1-3 feet)

## 🔒 Privacy & Security

- **Local Processing**: All hand detection happens locally on your device
- **No Data Collection**: No personal data is stored or transmitted
- **Camera Access**: Only used for real-time gesture detection

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [MediaPipe](https://mediapipe.dev/) - Google's framework for building perception pipelines
- [OpenCV](https://opencv.org/) - Open source computer vision library
- [PyAutoGUI](https://pyautogui.readthedocs.io/) - Cross-platform GUI automation library

## 📧 Contact

- **Author**: Your Name
- **Email**: your.email@example.com
- **Project Link**: https://github.com/yourusername/hand-volume-control

---

⭐ **Star this repository if you found it helpful!**
