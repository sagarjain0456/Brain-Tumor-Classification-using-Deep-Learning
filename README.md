# Brain Tumor Classification Using Deep Learning

## Overview

Brain tumors are serious medical conditions that require timely and accurate identification. Manual classification of brain MRI images can be time-consuming and may be subject to human error.

This project focuses on developing a deep learning-based system to classify brain MRI images into four categories using Transfer Learning, Convolutional Neural Networks (CNNs), and Ensemble Learning.

Three different deep learning models were implemented and evaluated. The best-performing approach combines a pretrained EfficientNetB3 model with a Sequential architecture and Ensemble Learning, achieving a **reported test accuracy of 99.8%**.

The project explores how pretrained deep learning architectures, data preprocessing, augmentation, regularization, and hyperparameter tuning can improve brain MRI image classification.

## Project Objectives

- Develop a deep learning model for brain tumor classification using MRI images.
- Classify MRI images into four different categories.
- Improve classification performance using Transfer Learning and pretrained CNN architectures.
- Address variations in tumor shapes, sizes, and locations.
- Apply data augmentation and regularization techniques to improve model generalization.
- Evaluate and compare multiple deep learning architectures using standard classification metrics.

## Dataset

The project uses the publicly available Brain Tumor MRI Dataset from Kaggle.

**Dataset source:**  
https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

The dataset is a combination of three datasets: Br35H, Figshare, and SARTAJ.

### Dataset Information

| Parameter | Details |
|---|---|
| Total images | 7,022 |
| Training images | 5,712 |
| Original testing directory images | 1,310 |
| Validation images | 655 |
| Final testing images | 655 |
| Number of classes | 4 |
| Image dimensions | 224 × 224 |
| Input channels | 3 (RGB) |
| Batch size | 16 |

**Dataset split:** The original testing directory contained 1,310 images, which were divided into 655 validation images and 655 final testing images.

### Classification Categories

1. **Glioma** – Tumor originating from glial cells.
2. **Meningioma** – Tumor originating from the meninges.
3. **Pituitary** – Tumor arising from the pituitary gland.
4. **No Tumor** – MRI images without a brain tumor.

## Models Implemented

Three different deep learning implementations were developed and evaluated.

### Model 1: EfficientNetB3 + Sequential Model + Ensemble Learning

**Reported test accuracy: 99.8%**

This is the highest-performing implementation in the project.

Key components:

- Pretrained EfficientNetB3 for feature extraction.
- Transfer Learning to utilize pretrained features.
- Sequential architecture with additional neural network layers.
- Batch Normalization to normalize layer activations.
- Dense layers for classification.
- Dropout Regularization to reduce overfitting.
- Ensemble Learning to combine predictions from independently trained model instances.
- Hyperparameter tuning for learning rate, dropout rate, and regularization strength.
- Adamax optimizer.

### Model 2: EfficientNetB3 + Sequential Model

**Reported test accuracy: 99.2%**

This implementation follows a similar architecture to Model 1, using EfficientNetB3 as the pretrained base model.

The main difference is that the model is trained once rather than combining predictions from multiple independently trained instances through Ensemble Learning.

### Model 3: DenseNet169

**Reported test accuracy: 96.7%**

This implementation uses a pretrained DenseNet169 architecture with the following additional layers:

- GlobalAveragePooling2D
- Dense layer with ReLU activation
- Dense layer with Softmax activation

This model provides an additional architecture for comparing classification performance.

## Methodology

The project follows the following workflow:

1. **Dataset Collection:** Obtain the Brain Tumor MRI dataset from Kaggle.
2. **Data Preparation:** Load MRI images and their corresponding class labels into Pandas DataFrames.
3. **Data Preprocessing:** Resize images to 224 × 224 pixels and use three input channels.
4. **Data Augmentation:** Apply image augmentation techniques to introduce variation into the image data.
5. **Feature Extraction:** Utilize pretrained EfficientNetB3 and DenseNet169 architectures.
6. **Transfer Learning:** Leverage pretrained model features for brain MRI classification.
7. **Model Development:** Build Sequential architectures and incorporate additional neural network layers.
8. **Optimization:** Apply regularization, dropout, Batch Normalization, and Adamax optimization.
9. **Ensemble Learning:** Combine predictions from multiple independently trained EfficientNetB3 model instances.
10. **Evaluation:** Assess model performance using accuracy, precision, recall, F1-score, and confusion matrices.

## Technologies and Tools Used

| Technology | Purpose |
|---|---|
| Python | Implementation |
| TensorFlow / Keras | Deep learning and model development |
| EfficientNetB3 | Pretrained feature extraction |
| DenseNet169 | Deep learning architecture |
| NumPy | Numerical operations |
| Pandas | Dataset handling |
| OpenCV | Image processing |
| PIL (Pillow) | Image handling |
| Scikit-learn | Dataset splitting and evaluation metrics |
| Matplotlib | Graphs and visualization |
| Seaborn | Data visualization |
| Kaggle | Dataset collection and notebook execution |
| Anaconda Navigator | Local development environment |
| Draw.io | Architecture diagrams |

## Evaluation Metrics

The models were evaluated using the following metrics:

- **Accuracy:** Measures the overall proportion of correctly classified images.
- **Precision:** Measures how many predicted positive classifications were correct.
- **Recall:** Measures how many actual positive cases were correctly identified.
- **F1-Score:** Represents the harmonic mean of precision and recall.
- **Confusion Matrix:** Provides a detailed comparison between actual and predicted classifications.

These metrics help evaluate classification performance beyond overall accuracy.

## Results and Model Comparison

The three implementations achieved the following reported test accuracies:

| Model | Test Accuracy |
|---|---:|
| EfficientNetB3 + Sequential + Ensemble Learning | **99.8%** |
| EfficientNetB3 + Sequential | **99.2%** |
| DenseNet169 | **96.7%** |

The EfficientNetB3-based ensemble approach achieved the highest reported test accuracy of 99.8%.

### Key Observations

- EfficientNetB3 performed well as a pretrained feature extraction architecture.
- Ensemble Learning improved the reported performance compared with the single-instance EfficientNetB3 implementation.
- The additional Sequential layers helped incorporate Batch Normalization, Dense layers, and Dropout Regularization.
- The dataset contained 7,022 images, providing a larger image collection than several smaller datasets discussed in the literature review.

## Project Highlights

- Implemented three different deep learning approaches.
- Worked with 7,022 brain MRI images.
- Performed four-class image classification.
- Utilized pretrained CNN architectures.
- Applied Transfer Learning and Ensemble Learning.
- Incorporated regularization and data augmentation techniques.
- Evaluated performance using multiple classification metrics.
- Compared results with previously published research.

## Screenshots

Selected screenshots documenting the project, model architectures, and classification results are available in the `screenshots/` directory.

## Future Work

The following improvements are identified for future development:

- Explore ensemble learning with more diverse deep learning architectures.
- Incorporate advanced data augmentation techniques.
- Improve model generalization and robustness.
- Investigate performance on additional and independent MRI datasets.

## Important Disclaimer

This project is an academic deep learning research implementation intended for educational and experimental purposes.

The reported classification accuracies do not establish clinical reliability. This model is not a substitute for professional medical evaluation, radiological interpretation, or diagnosis.

## References

**Dataset:**

Brain Tumor MRI Dataset – Kaggle  
https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

**Research References:**

The project includes a literature review of previously published research on brain tumor classification using CNNs, Transfer Learning, Ensemble Learning, and other deep learning approaches.

This repository presents the project's methodology, model architectures, comparative results, and selected visual documentation.

---

**Project Domain:** Artificial Intelligence | Deep Learning | Medical Image Classification | Computer Vision

**Project Type:** B.Tech Computer Science and Engineering Academic Research Project
