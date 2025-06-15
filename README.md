
# Multi-Camera People Tracking


## Overview

This project enhances standard surveillance systems by enabling **multi-camera people tracking**. While traditional surveillance cameras only record footage, this system detects, identifies, and tracks individuals across multiple video sources.

The system uses:

- **YOLOv4-tiny** for real-time object detection  
- **Omni-Scale Network (OSNet)** for person re-identification (ReID)

Together, these components allow for fast and accurate identity tracking across different camera views.

---

## Features

- Real-time object detection and tracking  
- Cross-camera person re-identification  
- Modular configuration via `config.yaml`  
- Visual and video output support

---

## Installation

Make sure Python 3.7.9 or newer is installed.

```bash
# Clone the repository
git clone  https://github.com/Saikrishna-Paila/Muti-Camera-people-tracking.git
cd multi-camera-people-tracking

# Install required packages
pip3 install -r requirements.txt

# Download pretrained models
python3 download_model.py
````

---

## Usage

Run the tracking script:

```bash
python3 main.py -h
```

### Command Line Arguments

```bash
usage: main.py [-h] [-s SOURCE_CONFIG_FILE]

optional arguments:
  -h, --help            Show this help message and exit
  -s SOURCE_CONFIG_FILE, --source-config-file SOURCE_CONFIG_FILE
                        Path to your config.yaml file
```

---

## Configuration File (`config.yaml`)

Customize the tracking pipeline by editing the `config.yaml` file:

```yaml
video_path:                         # Path to input video
object_detection_model_path:       # Path to YOLOv4-tiny weights
object_detection_classes_path:     # Path to class names file
feature_extraction_model_path:     # Path to OSNet model
size_each_camera_image:            # Image dimensions for each camera
resize_all_camera_image:           # Global resize factor for display
object_detection_threshold:        # Detection confidence threshold (e.g. 0.5)
feature_extraction_threshold:      # ReID similarity threshold (e.g. 0.6)
inference_model_device:            # Inference device ("cpu" or "cuda")
max_gallery_set_each_person:       # Number of frames to store per identity
display_video_camera_tracking:     # Show tracking output in a window (true/false)
save_video_camera_tracking:        # Save video output to disk (true/false)
fps_save_video_camera_tracking:    # FPS for saved video
output_path_name_save_video_camera_tracking: # Output directory
output_name_save_video_camera_tracking:      # Output video filename
```

---

## Example

```bash
python3 main.py -s config.yaml
```

---

## License

This project is licensed under the [MIT License]

---

## Author

Developed by **Saikrishna**


