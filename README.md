# 🌱 Plant Disease Detection and Solution

A simple **Plant Disease Detection and Solution** project using **Python, TensorFlow/Keras, CNN, OpenCV, and NumPy**.

The project uses image classification to identify plant diseases from leaf images. A Convolutional Neural Network (CNN) is trained using plant leaf images and then used to predict the disease class of a new image.

## 📌 About the Project

Plant diseases can affect crop growth and production. Early identification of plant diseases can help in taking appropriate preventive measures.

The main objective of this project is to build a basic image classification model that can identify plant diseases from leaf images.

The project contains:

* Plant leaf image dataset
* Image preprocessing
* Training and validation data
* CNN-based image classification
* Disease prediction
* Basic testing using new leaf images

## 🎯 Objectives

* Detect plant diseases using leaf images.
* Use CNN for image classification.
* Preprocess images before model training.
* Train the model using plant leaf images.
* Predict the disease class of a new image.
* Evaluate the performance of the trained model.

## 🛠️ Technologies Used

* **Python**
* **TensorFlow / Keras**
* **OpenCV**
* **NumPy**
* **Matplotlib**
* **Jupyter Notebook / Google Colab**

## 📊 Dataset

The project uses the **New PlantVillage** image dataset.

The dataset contains images belonging to **34 plant disease and healthy classes**.

Some examples include:

* Apple Apple Scab
* Apple Black Rot
* Apple Healthy
* Tomato Early Blight
* Tomato Late Blight
* Tomato Healthy
* Potato Early Blight
* Potato Late Blight
* Grape Black Rot
* Pepper Bell Healthy

The complete dataset is not included in this repository because of its large size.

## 🔄 Project Workflow

```text
Plant Leaf Dataset
        ↓
Dataset Extraction
        ↓
Train / Validation Split
        ↓
Image Preprocessing
        ↓
CNN Model
        ↓
Model Training
        ↓
Model Evaluation
        ↓
New Leaf Image
        ↓
Disease Prediction
```

## 📁 Dataset Preparation

The dataset is first downloaded and extracted.

The original dataset is stored in:

```text
/content/newplantvillage
```

The dataset is then divided into:

```text
80% → Training Data
20% → Validation Data
```

The project uses `split-folders` for splitting the dataset.

The resulting structure is:

```text
output/
│
├── train/
│   ├── Apple___Apple_scab/
│   ├── Apple___Black_rot/
│   ├── Apple___healthy/
│   └── ...
│
└── val/
    ├── Apple___Apple_scab/
    ├── Apple___Black_rot/
    ├── Apple___healthy/
    └── ...
```

The recorded dataset split contains:

* **50,368 training images**
* **12,611 validation images**
* **34 classes**

## 🖼️ Image Preprocessing

Before the images are given to the CNN, basic preprocessing is performed.

### Image Resizing

All images are resized to:

```text
200 × 200 × 3
```

where:

* `200` = image height
* `200` = image width
* `3` = RGB color channels

### Normalization

Pixel values are rescaled from:

```text
0 - 255
```

to:

```text
0 - 1
```

This helps provide normalized input to the neural network.

## 🤖 CNN Model

The project uses a **Convolutional Neural Network (CNN)** for image classification.

The basic architecture is:

```text
Input Image
     ↓
Convolution Layer
     ↓
Batch Normalization
     ↓
Max Pooling
     ↓
Convolution Layer
     ↓
Batch Normalization
     ↓
Max Pooling
     ↓
Convolution Layers
     ↓
Flatten
     ↓
Dense Layer
     ↓
Softmax Output
```

The input size is:

```text
200 × 200 × 3
```

The final output layer contains:

```text
34 classes
```

The Softmax layer provides the predicted class among the 34 classes.

## ⚙️ Model Training

The model is trained using:

* **Optimizer:** Adam
* **Loss Function:** Categorical Cross-Entropy
* **Epochs:** 12
* **Evaluation Metric:** Accuracy

The training data is provided using Keras `ImageDataGenerator` and `flow_from_directory`.

## 📈 Model Performance

The recorded training results show that the model achieved approximately:

```text
Training Accuracy:   99.30%
Validation Accuracy: 95.83%
```

The later validation evaluation reported approximately:

```text
Validation Accuracy: 95.84%
```

These results are based on the dataset and training configuration used in the notebook.

## 🧪 Testing the Model

For testing a new plant leaf image, place the image inside:

```text
/content/test_imgs/
```

Example:

```text
test_imgs/
│
├── leaf1.jpg
├── leaf2.jpg
└── leaf3.jpg
```

The testing process performs:

```text
Test Image
    ↓
Read using OpenCV
    ↓
Resize to 200 × 200
    ↓
Normalize pixel values
    ↓
CNN Model
    ↓
Predicted Class
```

The predicted class is then stored in a JSON file:

```text
prediction.json
```

Example output:

```json
{
    "leaf1.jpg": "Tomato___Early_blight",
    "leaf2.jpg": "Apple___healthy"
}
```

## 📂 Project Structure

```text
Plant-Disease-Detection-and-Solution/
│
├── README.md
│
├── plant_disease_detection.ipynb
│
├── test_imgs/
│   └── sample_leaf.jpg
│
├── model.h5
│
├── prediction.json
│
└── requirements.txt
```

> The complete dataset is not stored in this repository because of its large size.

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/lasya43/crop-disease-detection.git
```

### 2. Install the required libraries

```bash
pip install tensorflow
pip install opencv-python
pip install numpy
pip install matplotlib
pip install split-folders
```

Or install from:

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

Open:

```text
plant_disease_detection.ipynb
```

You can run the notebook using:

* Google Colab
* Jupyter Notebook
* VS Code

### 4. Prepare the dataset

Download and extract the plant disease dataset and provide the correct dataset path in the notebook.

### 5. Train the model

Run the dataset preparation, preprocessing, CNN creation and training cells.

### 6. Test an image

Place a leaf image inside:

```text
test_imgs/
```

and run the testing section of the notebook.

## 💡 Key Concepts Learned

This project demonstrates basic knowledge of:

* Python
* Image classification
* CNN
* Convolution layers
* Pooling
* Batch normalization
* Image preprocessing
* TensorFlow/Keras
* OpenCV
* Model training
* Model evaluation
* Disease prediction

## ⚠️ Limitations

* The model can predict only the classes included in the training dataset.
* Prediction can be affected by image quality and lighting conditions.
* Similar-looking diseases may be difficult to distinguish.
* The model should be considered an educational/project-level detection system and not a replacement for professional agricultural advice.

## 🔮 Future Improvements

Possible improvements include:

* Add more plant disease classes.
* Add more training images.
* Improve the CNN architecture.
* Use data augmentation.
* Add a user-friendly interface.
* Improve prediction confidence analysis.
* Add more detailed disease information and prevention recommendations.

## 👩‍💻 Project Summary

**Plant Disease Detection and Solution** is a CNN-based image classification project that identifies plant diseases from leaf images. The project demonstrates how computer vision and deep learning can be used to classify plant diseases using a trained CNN model.

### Main Pipeline

```text
Dataset
   ↓
Preprocessing
   ↓
CNN Training
   ↓
Model Evaluation
   ↓
Test Leaf Image
   ↓
Disease Prediction
```

## 📄 License

This project is intended for educational and learning purposes.
