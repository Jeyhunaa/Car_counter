# Car_counter

This project utilizes a combination of object detection and tracking techniques to identify and track vehicles in video footage. The primary tools used include the YOLOv8 model for object detection and SORT (Simple Online and Realtime Tracker) for tracking objects across frames.

## Tools and Techniques

### 1. YOLO (You Only Look Once) v8
- **Library**: `ultralytics` library provides the YOLOv8 model for detecting various objects, including vehicles like cars, trucks, buses, motorbikes, and bicycles.
- **Model Weights**: Pre-trained YOLOv8 models (`yolov8n.pt`, `yolov8m.pt`) are used to perform the object detection on the given video frames.

### 2. SORT (Simple Online and Realtime Tracker)
- **Tracking Algorithm**: SORT is an efficient algorithm for real-time object tracking that uses Kalman filters to predict the next state of the objects and associate them with detected objects using Intersection over Union (IoU).
- **Implementation**: A custom implementation of the SORT algorithm is used to track objects in video streams, particularly vehicles.

### 3. OpenCV
- **Library**: `opencv-python` is used for video processing, object tracking, and overlaying images such as masks and graphics onto the video frames.
- **Functions**: It is used to read video frames, process masks, apply bounding boxes, and manage graphical overlays.

### 4. cvzone
- **Library**: `cvzone` is used to overlay images (e.g., logos or graphics) onto video frames and to annotate bounding boxes with text and graphical elements.
- **Functions**: Provides functions like `overlayPNG` for image overlay and `cornerRect` for drawing rectangles with labels.

### 5. NumPy
- **Library**: `numpy` is used for handling array-based operations, storing detection results, and performing mathematical operations, especially in tracking and IoU calculations.

### 6. Masking and Region Selection
- **Techniques**: The region of interest is defined using a binary mask, which helps isolate specific areas in the video frames (e.g., vehicles within a specific area).
- **Application**: The mask is used to filter out the background and focus the detection process on specific parts of the video.

## File Structure

- `counter.py`: Main Python script for running the detection and tracking pipeline. It loads the YOLO model, applies object detection to video frames, tracks vehicles, and counts unique vehicles entering a defined region.
- `sort.py`: Implements the SORT algorithm, including Kalman filtering and object tracking logic.
- `requirements.txt`: Lists all the Python dependencies required to run the project.


## Notes

- The project processes video files using the YOLOv8 object detection model to identify vehicles. It then tracks those vehicles using the SORT algorithm and counts the unique vehicles that cross a specific region in the video.
- The project assumes the existence of a video file (`cars.mp4`) for processing.
- Custom masks and overlay images (e.g., logos) can be applied to video frames for visual enhancement.

