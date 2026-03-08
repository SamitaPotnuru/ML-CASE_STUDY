# AI Monument Recognition and Tourism Recommendation System

## Overview
This project is an **AI-based monument recognition system** that classifies historical monument images using **Deep Learning and Transfer Learning**.  
The model predicts the monument from an input image and provides a **tourism recommendation** related to that monument.

The system uses a **MobileNetV2 pretrained convolutional neural network (CNN)** which is trained on large datasets like ImageNet and adapted for custom image classification tasks through transfer learning.
---

## Dataset
Dataset used: **Indian Monuments Image Dataset**

Dataset structure:

```
Indian-monuments/
 ├── images
 │    ├── train
 │    │    ├── Taj_Mahal
 │    │    ├── Sun Temple Konark
 │    │    └── ...
 │    └── test
 │         ├── Taj_Mahal
 │         ├── Sun Temple Konark
 │         └── ...
```

Each folder contains images corresponding to a specific monument category.

---

## Technologies Used
- Python
- TensorFlow / Keras
- MobileNetV2 (Transfer Learning)
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- KaggleHub

---

## Installation

Install the required libraries:

```bash
pip install tensorflow pandas matplotlib seaborn opencv-python scikit-learn kagglehub
```

---

## Project Workflow

### 1. Dataset Download
Dataset is downloaded using KaggleHub.

```python
import kagglehub
path = kagglehub.dataset_download("danushkumarv/indian-monuments-image-dataset")
```

---

### 2. Data Exploration
- Count number of monument categories
- Count number of images in each category
- Visualize dataset distribution using bar plots

---

### 3. Image Preprocessing
Steps used for preprocessing:

- Read images using OpenCV
- Resize images to **128 × 128**
- Normalize pixel values (divide by 255)
- Convert labels to numeric values
- Split dataset into **training and testing sets**

---

## Model Architecture

The system uses **Transfer Learning with MobileNetV2**.

MobileNetV2 is a lightweight deep learning architecture designed for efficient image classification with lower computational cost while maintaining strong accuracy.
### Base Model
MobileNetV2 pretrained on ImageNet with the top layers removed.

### Custom Layers

```
GlobalAveragePooling2D
Dense (128, ReLU)
Dropout (0.5)
Dense (Softmax)
```

### Compilation

```
Optimizer: Adam
Loss Function: Categorical Crossentropy
Metric: Accuracy
```

---

## Model Training

Training configuration:

| Parameter | Value |
|----------|------|
| Image Size | 128x128 |
| Epochs | 5 |
| Batch Size | 32 |

The model learns to classify images into different monument categories.

---

## Model Evaluation

Model performance is evaluated using:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss

Graphs are generated to visualize learning performance.

---

## Monument Prediction

The model can predict a monument from an input image.

Example function:

```
recommend_structure(image_path)
```

Steps:
1. Load image
2. Resize and normalize
3. Predict monument category
4. Return tourism recommendation

---

## Example Output

```
Predicted Structure: Sun Temple Konark
Recommendation: Explore the architectural marvels of the Sun Temple in Konark, Odisha.
```

---

## Applications

- Tourism recommendation systems
- Cultural heritage recognition
- Smart travel assistants
- Educational AI systems
- Museum guide systems

---

## Future Improvements

- Train with larger datasets
- Apply data augmentation
- Increase training epochs
- Deploy as a web application
- Build a mobile tourism assistant app
- Implement real-time camera recognition

---
