# Bone Fracture Detection using ResNet152V2 🦴

## 📌 Project Overview
This project leverages **Deep Learning** and **Computer Vision** to automate the detection of bone fractures in X-ray images. Using a **Transfer Learning** approach with the **ResNet152V2** architecture, the model classifies images into two categories: `Fractured` and `Not_Fractured`. This solution addresses the challenge of identifying subtle fractures in medical imaging and provides a strong baseline for automated diagnostic support.

---

## 📊 Dataset Details
- **Dataset Source:** FracAtlas Dataset  
  https://figshare.com/articles/dataset/The_dataset/22363012
- **Problem Type:** Binary Classification
- **Classes:**
  - `Fractured`
  - `Not_Fractured`
- **Data Split:**
  - Training: 70%
  - Validation: 10%
  - Testing: 20%

---

## 🧠 Methodology & Architecture
The solution is built on **ResNet152V2**, a 152-layer deep residual network pre-trained on ImageNet.

### 1. Preprocessing Pipeline
- Image resizing to `(224 × 224)`
- Pixel normalization to range `[0, 1]`
- Data augmentation techniques:
  - Random rotation (5–10°)
  - Width & height shift (0.1)
  - Horizontal flip
  - Zoom and shear (0.1)

### 2. Model Architecture
- **Base Model:** ResNet152V2 (ImageNet weights, top layers removed)
- **Custom Classification Head:**
  - GlobalAveragePooling2D
  - Dense layer (128 units, ReLU)
  - Dropout (0.5)
  - Output Dense layer (Sigmoid)
- **Optimizer:** Adam (Learning Rate = 1e-4)
- **Loss Function:** Binary Crossentropy

---

## 📈 Experimental Results

| Metric | Score |
|------|------|
| **Test Accuracy** | **87.76%** |
| **Test AUC** | **0.8910** |
| **Test Loss** | **0.2835** |

### Classification Report
           precision    recall  f1-score   support

Fractured       0.73      0.48      0.58       143

Not_Fractured  0.90       0.96      0.93       674

 accuracy                           0.88       817



The model shows strong performance on non-fractured cases with an overall weighted F1-score of **0.87**.

---

## 🛠️ Tech Stack
- **Deep Learning:** TensorFlow, Keras
- **Model:** ResNet152V2 (Transfer Learning)
- **Data Processing:** NumPy, Pandas, Scikit-learn
- **Visualization:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook / Kaggle

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/rai-wasif/Bone-Fracture-Classification-ResNet152V2.git

### 2. Install Dependencies

pip install -r requirements.txt

3. Run the Notebook

Open Bone_Fracture_Classification.ipynb and run all cells.
Make sure to update BASE_INPUT_PATH to your local dataset directory.
👤 Author

Muhammad Wasif
Department of Artificial Intelligence & Data Science
FAST – National University of Computer and Emerging Sciences (FAST-NUCES)
