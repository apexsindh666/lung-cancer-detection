# lung-cancer-detection
mode to detect lung cancer
# 🩺 Lung & Colon Cancer Classification using CNN (ResNet50 + Grad-CAM)

This project implements a deep learning pipeline to classify **lung and colon cancer histopathological images** using a transfer learning approach with **ResNet50**.  
Additionally, the project includes **Grad-CAM visualization** to highlight important regions in the images influencing the model’s predictions.  

---

## 📂 Dataset
The dataset is sourced from [Kaggle](https://www.kaggle.com/datasets/andrewmvd/lung-and-colon-cancer-histopathological-images).  
It contains histopathological images of lung and colon tissues categorized as **cancerous** and **non-cancerous**.  

- **Training set:** `lung_cancer_dataset/train`  
- **Validation set:** `lung_cancer_dataset/val`  
- **Test set:** `lung_cancer_dataset/test`  

---

## ⚙️ Methodology
1. **Data Preprocessing**  
   - Image resizing to `224x224`  
   - Normalization (rescale = `1/255`)  
   - Data generators for train/val/test splits  

2. **Model Architecture**  
   - Base Model: **ResNet50 (pretrained on ImageNet, frozen)**  
   - Added layers:  
     - GlobalAveragePooling2D  
     - Dense (64, ReLU)  
     - Dropout (0.5)  
     - Dense (1, Sigmoid)  

3. **Training**  
   - Optimizer: Adam (`lr=1e-3`)  
   - Loss: Binary Crossentropy  
   - Metrics: Accuracy  
   - Debug training run: 1 epoch  

4. **Evaluation**  
   - Accuracy evaluated on test set  
   - Grad-CAM visualizations for interpretability  

---

## 📊 Results
- **Test Accuracy:** ~X% (replace with your final trained result)  
- Grad-CAM successfully highlights cancer-relevant regions in histopathological images.  

---

## 📸 Sample Output (Grad-CAM)
Example heatmap overlay showing model focus regions:  

![Grad-CAM Example](gradcam_example.png)  

---

## 🚀 How to Run
```bash
# Clone repo
git clone https://github.com/your-username/lung-cancer-classification.git
cd lung-cancer-classification

# Install dependencies
pip install -r requirements.txt

# Run training (Jupyter/Colab)
jupyter notebook Lung_Cancer_CNN.ipynb
