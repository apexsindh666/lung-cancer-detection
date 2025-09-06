# Lung & Colon Cancer Detection

## Overview
This project detects **lung and colon cancer** from histopathology images using **MobileNetV2**. It also uses **Grad-CAM** to highlight cancerous regions in the images.

## Dataset
- Kaggle: [Lung and Colon Cancer Histopathological Images](https://www.kaggle.com/datasets/kmader/100k-histopathology-images)  
- Classes: `colon_aca`, `colon_n`, `lung_aca`, `lung_n`, `lung_scc`  
- Labels mapped to **Cancer / Normal**

## Features
- MobileNetV2 classifier (CPU-compatible)  
- Grad-CAM heatmaps for visual explanations  
- Generates visual reports (PNG) of predictions

## Installation

'''bash
git clone https://github.com/<your-username>/lung-colon-cancer-detection.git
pip install torch torchvision matplotlib pillow opencv-python



##Usage
Load the trained model
Visualize predictions and Grad-CAM overlays
Save report:

                from gradcam_report import save_gradcam_report
dataset_folder = "/path/to/lung_colon_image_set"
save_gradcam_report(dataset_folder, images_per_class=2, save_path="gradcam_report.png")


##Results
~93% test accuracy
Grad-CAM highlights cancer regions for interpretability
