SHRiii — Brain Hemorrhage Detection and Classification Using Deep Learning

> **Project Status: In Progress**  
> SHRiii is currently under development. The complete project and final documentation will be uploaded after implementation and testing are finished.

SHRiii is a deep-learning project focused on classifying brain CT scan images to explore AI-assisted identification of intracranial hemorrhage. The project uses a Convolutional Neural Network (CNN) workflow and is intended to grow into an accessible application with model-evaluation visualizations and statistical analysis.

> **Medical disclaimer:** SHRiii is a research and educational project, not a medical device. It must not be used to diagnose or rule out a brain hemorrhage, guide treatment, or replace assessment by a qualified healthcare professional.

---

## Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Planned Workflow](#planned-workflow)
- [Technology Stack](#technology-stack)
- [Classification Tasks](#classification-tasks)
- [Model Training](#model-training)
- [Evaluation](#evaluation)
- [Application Roadmap](#application-roadmap)
- [Project Structure](#project-structure)
- [Setup](#setup)
- [Run the Project](#run-the-project)
- [Current Status and Results](#current-status-and-results)
- [Limitations and Responsible Use](#limitations-and-responsible-use)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

## Overview

Brain hemorrhage is a serious medical emergency. CT imaging is commonly used by healthcare professionals when investigating suspected intracranial bleeding. This project explores whether deep-learning methods can classify labeled CT scan images and support research into faster image analysis.

The model workflow described for SHRiii includes image preprocessing, CNN-based feature learning, classification, prediction, and performance evaluation. The project description reports **12,478 CT scan images**; the dataset source, exact class distribution, split method, and final test results will be documented after they have been verified against the project files and experiments.

SHRiii is being developed in stages. The planned user interface and R-based statistical dashboard are not represented as completed features until they have been implemented and tested.

## Objectives

- Develop a CNN-based workflow for brain CT image classification.
- Preprocess and normalize images consistently.
- Explore binary and multi-class classification where supported by the dataset and trained model.
- Evaluate model performance using multiple metrics rather than accuracy alone.
- Build a simple interface for submitting images and viewing model outputs.
- Add statistical visualizations and reporting to make model evaluation easier to inspect.
- Explore explainability tools such as Grad-CAM as a future enhancement.

## Dataset

The project description reports **12,478 CT scan images**. Before publishing experimental conclusions, document the dataset's name and source, permitted use, class labels, class counts, annotation method, and train/validation/test split.

Potential class labels, depending on the dataset version and the model configuration, include:

- Normal
- Epidural hemorrhage
- Subdural hemorrhage
- Intraparenchymal hemorrhage
- Intraventricular hemorrhage
- Subarachnoid hemorrhage

These are possible labels, not a claim that every listed class is currently supported by the trained model. The model's output layer and class mapping must match the labels used during training.

### Data-handling practices

- Check image files and labels before training.
- Record the number of images in each class.
- Keep training, validation, and test sets separate.
- Apply augmentation to training data only.
- Where patient identifiers are available, split data by patient to reduce data leakage.
- Do not upload private, identifiable, or restricted medical images to a public repository.

## Planned Workflow

```text
Labeled CT Scan Images
          |
          v
Data Validation and Cleaning
          |
          v
Train / Validation / Test Split
          |
          v
Image Preprocessing
(Resize and Normalize)
          |
          v
CNN Training
          |
          v
Prediction on Held-Out Data
          |
          v
Evaluation and Visualization
          |
          v
Application Interface (Planned)
```

The exact preprocessing steps and split strategy should match the implementation and be documented once verified.

## Technology Stack

| Area | Technology |
|---|---|
| Programming language | Python |
| Deep learning | TensorFlow, Keras |
| Image processing | OpenCV |
| Numerical computing | NumPy |
| Data handling | Pandas |
| Evaluation metrics | Scikit-learn |
| Plotting | Matplotlib |
| Development tools | Visual Studio Code, Git, GitHub |
| Statistical dashboard | R and Shiny — planned |
| Python–R integration | `reticulate` or an API — to be selected during implementation |

The table distinguishes the Python stack described for the model from application components that are still planned.

## Classification Tasks

The project can be configured for a classification task supported by the selected dataset and trained model.

### Binary classification

- Normal
- Hemorrhage

### Multi-class classification

Potentially distinguish among normal scans and specific hemorrhage types when the dataset contains reliable labels for those classes and the model has been trained for that task.

A model trained for binary classification cannot automatically provide reliable hemorrhage subtype predictions without suitable multi-class training and evaluation.

## Model Training

The described CNN training workflow includes:

1. **Forward propagation:** The model processes an image and produces output scores.
2. **Loss calculation:** The loss function compares the predictions with the known labels.
3. **Backpropagation:** Gradients are calculated to update the model's weights.
4. **Optimization:** An optimizer such as Adam updates the weights.
5. **Validation:** Model performance is checked on data not used to update its weights.
6. **Testing:** Final performance is measured on a held-out test set.

Potential training choices, depending on the implementation:

- **Optimizer:** Adam
- **Binary classification loss:** Binary cross-entropy
- **Multi-class classification loss:** Categorical cross-entropy for one-hot labels or sparse categorical cross-entropy for integer labels

The architecture, input size, batch size, number of epochs, learning rate, and loss configuration should be recorded from the actual training code. These settings should not be inferred from the README alone.

## Evaluation

Accuracy by itself can hide poor performance on a minority class. The evaluation plan includes the following metrics:

| Metric | Meaning |
|---|---|
| Accuracy | Proportion of all predictions that are correct |
| Precision | Proportion of predicted positive cases that are actually positive |
| Recall / Sensitivity | Proportion of actual positive cases correctly identified |
| Specificity | Proportion of actual negative cases correctly identified |
| F1-score | Harmonic mean of precision and recall |
| Confusion matrix | Counts of correct and incorrect predictions by class |

For a medical-image research project, false negatives and class-specific performance deserve particular attention. Report the test-set size, class distribution, split method, and per-class metrics along with any aggregate score.

### Results

**Final evaluation results have not been added to this README.** Results should be reported only after running a reproducible evaluation on held-out test data.

| Metric | Result |
|---|---|
| Accuracy | Not reported |
| Precision | Not reported |
| Recall / Sensitivity | Not reported |
| Specificity | Not reported |
| F1-score | Not reported |

Do not claim clinical validation, improved patient outcomes, or a specific level of diagnostic accuracy without appropriate evidence.

## Application Roadmap

The following features are planned and should be marked as complete only after implementation and testing.

- [ ] Simple interface for uploading a CT scan image.
- [ ] Display the predicted class and model output score.
- [ ] R/Shiny dashboard for statistical summaries and evaluation charts.
- [ ] Confusion-matrix and classification-metric visualizations.
- [ ] Grad-CAM visualization, if compatible with the final model.
- [ ] Export evaluation summaries to CSV or PDF.
- [ ] Optional prediction history, with appropriate privacy safeguards.

### Planned statistical dashboard

The R/Shiny dashboard may present:

- Dataset size and class distribution.
- Model-evaluation metrics.
- Confusion matrix and charts.
- Comparisons between model versions.
- Exportable evaluation summaries.

Statistical methods will be selected according to the question and data structure. A p-value alone does not establish clinical importance, safety, or superiority.

## Project Structure

The repository description proposes the following layout. Update it to match the files actually committed to GitHub.

```text
Brain-Hemorrhage-Detection/
├── dataset/          # Local dataset; do not commit restricted images
├── models/           # Saved model files, if included
├── screenshots/      # Application screenshots, when available
├── src/              # Source code
├── outputs/          # Local evaluation outputs
├── requirements.txt  # Python dependencies
├── main.py           # Application or project entry point
├── README.md
└── LICENSE
```

## Setup

### Prerequisites

- Python 3.9 or a version compatible with the TensorFlow release used by the project.
- Git.
- Sufficient disk space and memory for the dataset and model.
- R and RStudio only when the planned R/Shiny dashboard is implemented.

### 1. Clone the repository

```bash
git clone https://github.com/onkar2412/Brain-Hemorrhage-Detection.git
cd Brain-Hemorrhage-Detection
```

### 2. Create and activate a virtual environment

**Windows**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**macOS / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Make sure `requirements.txt` lists the dependencies and versions required by the actual code. TensorFlow installation compatibility varies by Python version and operating system.

### 4. Prepare the data and model

- Obtain the dataset from its authorized source.
- Arrange the images and labels in the format expected by the data-loading code.
- Confirm the saved model path and class-label mapping.
- Keep restricted medical data out of the public repository.

## Run the Project

If `main.py` is the configured entry point, run:

```bash
python main.py
```

The command and expected output must be confirmed against the current implementation before the repository is described as runnable. The typical inference process is to load a trained model, validate and preprocess an input image, run inference, map the output to the correct class label, and display the result.

A model output score must not be presented as a patient's calibrated probability of disease unless calibration has been properly evaluated.

## Current Status and Results

SHRiii is **under development**. The complete project and final documentation will be uploaded after implementation and testing are finished.

The model description and technology stack above reflect the project scope provided for this README. The final repository should include verified setup instructions, the actual dataset details, implemented feature status, and reproducible evaluation results. Planned features must not be described as already available.

## Limitations and Responsible Use

- Model performance depends on dataset quality, labels, preprocessing, and representativeness.
- Results on one dataset may not generalize to other hospitals, scanners, or patient populations.
- Data leakage can make evaluation results misleading.
- A classifier does not necessarily locate or outline bleeding regions unless it is specifically designed and validated for localization.
- Grad-CAM, if added, is an explanatory visualization and not proof that a prediction is medically correct.
- This project is not a substitute for professional medical review or emergency care.
- Do not upload identifiable medical images to public services without authorization and appropriate privacy safeguards.

## Future Work

- Complete and test the image-upload interface.
- Implement the R/Shiny statistical dashboard.
- Add and evaluate explainability visualizations.
- Compare CNN architectures using the same appropriate data-splitting strategy.
- Improve reporting with per-class metrics and error analysis.
- Add CSV/PDF report export.
- Consider deployment only after reviewing security, privacy, model limitations, and hosting constraints.

## Contributing

Contributions are welcome once the repository is available for collaboration.

1. Fork the repository.
2. Create a feature branch.
3. Implement and test the change.
4. Commit with a descriptive message.
5. Open a pull request describing the change.

Do not contribute patient-identifiable or otherwise restricted data.

## License

The project description specifies the MIT License. Include a valid `LICENSE` file in the repository before presenting the project as MIT-licensed. Check that the dataset and any pretrained weights have licenses compatible with the intended use; the project's code license does not automatically license third-party data.

## Author

**Onkar Shrikonda**

AI & Data Science Engineer | Python Developer | Computer Vision and Healthcare AI

- GitHub: [onkar2412](https://github.com/onkar2412)
- LinkedIn: [onkar-shrikonda](https://www.linkedin.com/in/onkar-shrikonda/)

---

Please preserve dataset attribution, licensing requirements, and the research-only limitations when using or extending this project.
'''

