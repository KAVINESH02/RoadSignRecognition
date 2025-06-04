# 🚦 Road Sign Recognition using CNN & PyQt5

This repository contains a **Python application** that performs traffic sign recognition using a **Convolutional Neural Network (CNN)**. The application provides a **PyQt5-based graphical user interface (GUI)** with three main functions:

1. **🧠 Training**  
   Trains a CNN from scratch on a labeled traffic-sign dataset.

2. **🖼️ Browse Image**  
   Allows the user to select an input image from their local file system to be classified.

3. **🎯 Classify**  
   Loads the trained model from disk, processes the selected image, and displays the predicted sign name in the GUI.

Under the hood, we use **Keras** (with a TensorFlow backend) to build and train a CNN that takes RGB traffic-sign images (resized to 30×30 pixels) and outputs a probability distribution over **43 possible sign classes** (from the German Traffic Sign Recognition Benchmark [GTSRB] dataset).

---

## ⚙️ Features

### 1. Interactive GUI (PyQt5)
- **Browse Image**  
  Select any `.png`, `.jpg`, `.jpeg`, or `.bmp` image from disk.

- **Training**  
  Trigger model training on the prepared dataset and view progress in the console.

- **Classify**  
  Load a pre-trained `.h5` model file and predict the class of a newly selected image.

- **Result Display**  
  The recognized class name appears in a read-only text box.

### 2. Custom CNN Architecture (Keras)
- **Block 1**  
  - Conv2D → Conv2D → MaxPool2D → Dropout  
  - (filters: 32, kernel sizes: 5×5, activation: ReLU)

- **Block 2**  
  - Conv2D → Conv2D → MaxPool2D → Dropout  
  - (filters: 64, kernel sizes: 3×3, activation: ReLU)

- **Dense Layers**  
  - Flatten → Dense(256, ReLU) → Dropout → Dense(43, Softmax)

### 3. Training Visualization (Matplotlib)
- Saves plots of **training/validation accuracy** (`Accuracy1.png`) and **training/validation loss** (`Loss1.png`) to disk.

### 4. Model Persistence
- After training, the model is saved to `my_model_new.h5`.  
- During classification, the code loads `my_model.h5` by default (or `my_model_new.h5` if retrained).

---

## 📁 Folder Structure

road-sign-recognition/
├── dataset/
│ └── train/
│ ├── 0/ to 42/ # 43 folders with traffic sign images
├── Accuracy1.png # Accuracy graph (after training)
├── Loss1.png # Loss graph (after training)
├── my_model.h5 # Optional pre-trained model
├── my_model_new.h5 # Trained model after clicking "Training"
├── requirements.txt # Python dependencies
├── main.py # Launches the GUI
└── README.md # This file

yaml
Copy
Edit

