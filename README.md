Based on the structure of your project, here's a proposed `README.md` file to provide clear documentation: 

---

# YOLO Object Detection with Kafka Integration

This project integrates **YOLOv8**, **OpenCV**, and **Kafka** to perform real-time object detection using images and videos. It supports capturing webcam inputs, sending them through Kafka for processing, and detecting objects with YOLOv8.

## Features

- Real-time object detection with YOLOv8.
- Integration with Kafka for message exchange.
- Capture and process images/videos from the webcam.
- Visualize detections with bounding boxes and confidence scores.

## Directory Structure

```
.
├── Main.ipynb               # Main notebook for processing
├── commands.ipynb           # Kafka setup commands
├── detection_webcam_images.ipynb  # Image capture and processing
├── detection_webcam_videos.ipynb  # Video capture and processing
├── envoi                    # Folder containing example files
│   ├── 1.png
│   ├── 2.png
│   ├── 3.png
│   ├── bikes.mp4
│   ├── mask.png
│   └── motorbikes.mp4
├── yolov8n.pt               # YOLOv8 model weights
├── .gitignore               # Ignored directories
```

## Prerequisites

1. Install Python 3.7 or higher.
2. Install required libraries:
   ```bash
   pip install ultralytics opencv-python confluent-kafka
   ```
3. Ensure **Kafka** is installed and running on your system.
   - You can use the scripts in `commands.ipynb` to manage Kafka and ZooKeeper.

## Usage

### 1. Start Kafka
Use the provided commands to start Kafka and ZooKeeper:
```bash
zookeeper-server-start.sh /path/to/zookeeper.properties
kafka-server-start.sh /path/to/server.properties
```

### 2. Run Object Detection
You can run the notebooks based on your requirements:
- `detection_webcam_images.ipynb`: For image-based detection.
- `detection_webcam_videos.ipynb`: For video-based detection.

### 3. View Results
Captured images and videos are stored in their respective folders:
- Captured images: `captured_images`
- Processed images: `received_images`

The output will include bounding boxes, class names, and confidence scores overlaid on images or videos.

## Configuration

### Kafka Settings
Update the Kafka `bootstrap.servers` configuration in the code with your Kafka server's address:
```python
'bootstrap.servers': "localhost:9092",
```

