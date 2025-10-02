# AI-Powered Plant Disease Detection and Remedy Recommendation

## Description
Developed an end-to-end system to detect plant leaf diseases and recommend remedies using computer vision and generative AI. The project uses the **PlantDoc dataset** and **YOLOv5** for disease detection, and leverages **Google Gemini API** to provide remediation suggestions. A **Streamlit web app** offers a user-friendly interface for image upload, detection, and remedy output.

## Key Features
- **Dataset Preparation:** Processed 2,482 images with 8,595 labeled objects across 29 classes. Converted JSON annotations to YOLO-compatible `.txt` labels for training.
- **Model Development:** Trained a YOLOv5 model for multi-class leaf disease detection with accurate bounding boxes.
- **Generative AI Integration:** Integrated **Gemini API** to generate actionable remediation advice for detected diseases.
- **Web Deployment:** Built a **Streamlit interface** for users to upload leaf images, visualize detection results, and receive remedy suggestions.
- **Technical Stack:** Python, PyTorch, YOLOv5, Streamlit, Google Gemini API.

## Implementation Details
1. **Data Loading & Preprocessing**
   - Loaded images via PIL; bounding box coordinates and labels stored in dictionaries.
   - Converted annotations to YOLO `.txt` format with `class_id x_center y_center width height`.

2. **Model Training**
   - Used `yolov5s` model, trained with 20 epochs, batch size 15, image size 640×640.
   - Data split: 2,251 train images, 231 test images.
   - Monitored training using YOLOv5 runs folder with weights, validation graphs, and predicted bounding boxes.

3. **Detection & Remedy Recommendation**
   - Detected diseases using `detect.py`.
   - Predictions passed to **Gemini API** to generate customized remediation advice.
   - Pipeline handles both successful and fallback detection scenarios.

4. **Deployment**
   - Streamlit web app for real-time interaction.
   - Users can upload images and receive instant detection results with remedy suggestions.

## Dataset
- **PlantDoc Dataset:** [PlantDoc Dataset](https://datasetninja.com/plantdoc)  
  - 2,482 images, 29 disease classes
  - Bounding box annotations for all images

## Installation
1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd <repo-folder>
2. Set up the environment:
    ```bash
      conda env create -f environment.yml
      conda activate tf_gpu

3. Create
   ```bash
   config.json with dataset and model paths.

6. Run the web app:
   ```bash
    streamlit run --server.enableCORS false --server.enableXsrfProtection false app.py

# Usage

1. Upload a plant leaf image.

2. The system detects diseases and highlights them with bounding boxes.

3. Remedy recommendation is generated via Gemini API.

# References

- YOLOv5

- PlantDoc Dataset

- Streamlit

- Google Gemini API

# Contributors

Ipsa Badoniya
