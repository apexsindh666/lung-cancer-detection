Lung & Colon Cancer Detection using MobileNetV2 & Grad-CAM


🔬 Project Overview
This project uses deep learning to detect lung and colon cancer from histopathological images. It leverages MobileNetV2 for classification and Grad-CAM to visualize regions of the image that contribute most to the model's prediction.
The model predicts whether an image belongs to Cancer or Normal tissue, and provides visual heatmaps for interpretability.



📂 Dataset
The dataset used is Lung and Colon Cancer Histopathological Images from Kaggle.


Structure after caching:
lung_colon_image_set/
├── colon_image_sets/
│   ├── colon_aca/   # Cancer
│   └── colon_n/     # Normal
└── lung_image_sets/
    ├── lung_aca/    # Cancer
    ├── lung_n/      # Normal
    └── lung_scc/    # Cancer


Classes: colon_aca, colon_n, lung_aca, lung_n, lung_scc
The model maps these to Cancer / Normal labels for predictions.


🛠 Features
MobileNetV2 for efficient classification on CPU.
Grad-CAM visualization to highlight cancerous regions in images.
Predicts Cancer / Normal for histopathology images.
Generates visual reports (PNG) of predictions with Grad-CAM overlays.
Fully CPU-compatible, no GPU required.


⚡ Installation
# Clone repository
git clone https://github.com/<your-username>/lung-colon-cancer-detection.git
cd lung-colon-cancer-detection

# Install dependencies
pip install torch torchvision matplotlib pillow opencv-python
🚀 Usage
1️⃣ Training the Model
# Load dataset
# Define MobileNetV2 model
# Train with your training set
Training can be done on CPU, but using GPU will speed it up significantly.
2️⃣ Load Pre-trained Model & Grad-CAM Visualization
# Load the trained model
# Define Grad-CAM target layer
# Visualize predictions with Grad-CAM
3️⃣ Generate Grad-CAM Report
from gradcam_report import save_gradcam_report

dataset_folder = "/content/drive/MyDrive/ColabCache/lung_colon_dataset/lung_colon_image_set"
save_gradcam_report(dataset_folder, images_per_class=2, save_path="gradcam_report.png")
📊 Results
Model achieved ~90% test accuracy on 5-class lung and colon dataset.
Grad-CAM highlights regions indicative of cancer for visual interpretability.
Report saved as gradcam_report.png can be used for presentations or documentation.
📌 References
MobileNetV2 Paper
Grad-CAM Paper
Kaggle Dataset: Lung and Colon Cancer Histopathological Images
📝 License
This project is released under the MIT License.
