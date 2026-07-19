# Brain Hemorrhage Detection and Classification Using Deep Learning

> An AI-powered medical imaging system that detects and classifies brain hemorrhages from CT scan images using Convolutional Neural Networks (CNNs).

---

## Description / Overview

Brain Hemorrhage Detection and Classification Using Deep Learning is a medical image analysis project that leverages Convolutional Neural Networks (CNNs) to automatically detect intracranial hemorrhages from CT scan images.

The primary objective of the system is to assist radiologists and healthcare professionals by providing faster, more reliable, and automated diagnosis of brain bleeding, reducing diagnostic delays and improving clinical decision-making during emergencies.

The model was trained on **12,478 CT scan images** and performs image preprocessing, feature extraction, CNN-based classification, performance evaluation, and prediction.

---

## Features

- Automated brain hemorrhage detection from CT scans
- CNN-based deep learning classification
- Medical image preprocessing pipeline
- Image normalization and augmentation
- Binary and multi-class classification support
- High-performance medical image analysis
- Performance evaluation using multiple metrics
- AI-assisted diagnostic workflow

---

## Problem Statement

Brain hemorrhage is one of the most critical neurological emergencies where early diagnosis can significantly improve patient survival.

Manual examination of CT scans is:

- Time-consuming
- Prone to human error
- Challenging during emergency situations

This project aims to develop an AI-based solution capable of automatically detecting brain hemorrhages with high accuracy to assist healthcare professionals.

---

## Objectives

- Detect brain hemorrhages automatically from CT scans
- Reduce diagnosis time
- Assist radiologists in clinical decision-making
- Improve diagnostic accuracy using Deep Learning
- Reduce false positives and false negatives
- Enable AI-assisted emergency healthcare screening

---

## Dataset

The model was trained using **12,478 CT scan images**.

The dataset includes CT scans belonging to categories such as:

- Normal Brain
- Epidural Hemorrhage
- Subdural Hemorrhage
- Intraparenchymal Hemorrhage
- Intraventricular Hemorrhage
- Subarachnoid Hemorrhage

> Depending on the dataset version, the project can also be configured for binary classification (Normal vs. Hemorrhage).

---

## Project Workflow

```text
CT Scan Images
       │
       ▼
Image Preprocessing
       │
       ▼
Image Normalization
       │
       ▼
Train/Test Split
       │
       ▼
CNN Model
       │
       ▼
Feature Learning
       │
       ▼
Classification
       │
       ▼
Performance Evaluation
       │
       ▼
Prediction
```

---

## Medical Image Preprocessing

To improve model performance, several preprocessing techniques were applied:

- Image Resizing
- Image Normalization
- Data Cleaning
- Data Augmentation
- Noise Reduction
- Dataset Balancing

### Data Augmentation Techniques

- Rotation
- Horizontal Flip
- Zoom
- Width Shift
- Height Shift
- Brightness Adjustment

Benefits:

- Improves generalization
- Prevents overfitting
- Increases dataset diversity

---

## CNN Architecture

The Convolutional Neural Network automatically learns important medical features from CT images.

```text
Input Layer
      │
      ▼
Convolution Layer
      │
      ▼
ReLU
      │
      ▼
Max Pooling
      │
      ▼
Convolution Layer
      │
      ▼
ReLU
      │
      ▼
Max Pooling
      │
      ▼
Flatten
      │
      ▼
Dense Layer
      │
      ▼
Dropout
      │
      ▼
Output Layer
```

The CNN extracts:

- Brain tissue structures
- Bleeding regions
- Blood clots
- Texture differences
- Edge information

---

## Model Training

Training involved:

- Forward Propagation
- Loss Calculation
- Backpropagation
- Weight Optimization

### Optimizer

- Adam

### Loss Function

- Binary Cross Entropy (Binary Classification)
- Categorical Cross Entropy (Multi-class Classification)

---

## Model Evaluation

The model was evaluated using unseen CT scan images.

Evaluation metrics include:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

These metrics help assess the reliability and robustness of the model in medical diagnosis.

---

## Technologies Used

### Programming Language

- Python

### Frameworks & Libraries

- TensorFlow
- Keras
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

### Concepts

- Deep Learning
- Computer Vision
- Medical Image Processing
- CNN
- Binary Classification
- Multi-class Classification

### Tools

- Visual Studio Code
- Git
- GitHub

---

## Project Structure

```text
Brain-Hemorrhage-Detection/
│
├── dataset/
├── models/
├── screenshots/
├── src/
├── outputs/
├── requirements.txt
├── README.md
├── LICENSE
└── main.py
```

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/onkar2412/Brain-Hemorrhage-Detection.git
```

### Navigate to the Project

```bash
cd Brain-Hemorrhage-Detection
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Usage

Run the application:

```bash
python main.py
```

The system preprocesses CT scan images, performs prediction using the trained CNN model, and classifies the input as either a hemorrhage type or a normal brain scan.

---

## Requirements

- Python 3.9+
- TensorFlow
- Keras
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

---

## Results

The developed system successfully:

- Detects brain hemorrhages from CT scan images
- Learns discriminative medical features using CNNs
- Performs automatic classification
- Reduces dependency on manual inspection
- Demonstrates the potential of AI-assisted healthcare diagnostics

---

## Challenges Faced

- Class imbalance between hemorrhage types
- Similar appearance of certain hemorrhage categories
- Limited annotated medical datasets
- High computational requirements
- Preventing model overfitting

---

## Future Enhancements

- Implement ResNet50, DenseNet121, EfficientNet, and Vision Transformers (ViT)
- Integrate Grad-CAM for explainable AI
- Develop a Flask or FastAPI web application
- Deploy the model to cloud platforms
- Extend detection to brain tumors, ischemic stroke, and skull fractures
- Optimize for edge devices used in hospitals

---

## Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a new feature branch.
3. Commit your changes.
4. Push your branch.
5. Open a Pull Request.

---

## License

This project is licensed under the MIT License.

See the **LICENSE** file for complete details.

---

## Acknowledgments

- TensorFlow
- Keras
- OpenCV
- Scikit-learn
- Medical Imaging Research Community
- Python Community

---

## Author

**Onkar Shrikonda**

AI & Data Science Engineer | Python Developer | Computer Vision & Healthcare AI Enthusiast

---

## Contact

**GitHub:** https://github.com/onkar2412

**LinkedIn:** https://www.linkedin.com/in/onkar-shrikonda/

**Email:** shrikonda.onkar@gmail.com
