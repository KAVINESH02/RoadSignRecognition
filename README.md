# 🚦 Road Sign Recognition using CNN and PyQt5

This repository contains a Python-based desktop application for recognizing traffic signs using a custom Convolutional Neural Network (CNN). It features an interactive GUI built with PyQt5 that enables training a model, browsing traffic sign images, and classifying them with real-time output.

---

## 📌 Project Features

- **Interactive GUI (PyQt5)**:
  - 🖼️ **Browse Image**: Select .png/.jpg/.jpeg/.bmp files.
  - 🧠 **Train Model**: Train a CNN from scratch.
  - ✅ **Classify Image**: Use a pre-trained model to predict the sign.
  - 📢 **Result Display**: Recognized class is shown in a text box.

- **Model Architecture (Keras)**:
  - 2 blocks of Conv2D → Conv2D → MaxPool2D → Dropout
  - Flatten → Dense(256) → Dropout → Dense(43) with softmax

- **Training Visualization**:
  - Saves plots of accuracy and loss (`Accuracy1.png`, `Loss1.png`).

- **Model Handling**:
  - Trained model saved as `my_model_new.h5`
  - Loaded model during classification: `my_model.h5`

---

## 📁 Folder Structure
```
road-sign-recognition/
├── dataset/train/0/ to 42/
├── Accuracy1.png
├── Loss1.png
├── my_model.h5
├── my_model_new.h5
├── requirements.txt
├── main.py
└── README.md
```

---

## ⚙️ Dependencies
Install Python 3.7+ and run:
```
pip install -r requirements.txt
```
**requirements.txt**:
- PyQt5
- numpy
- Pillow
- matplotlib
- scikit-learn
- tensorflow
- keras

---

## 📦 Installation Steps
```bash
git clone https://github.com/<your-username>/road-sign-recognition.git
cd road-sign-recognition
python3 -m venv venv
source venv/bin/activate  # For Windows: venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 📊 Training the Model
```bash
python main.py
```
- Click “Training” → Model trains on dataset (5 epochs).
- Training & validation performance shown in console.
- Model saved to `my_model_new.h5`.

---

## 🧪 Classifying Images
```bash
python main.py
```
- Click **Browse Image** to select a traffic sign.
- Click **Classify** → Model predicts class name.
- Displays result like `"Stop"` in GUI.

---

## 🧠 Model Summary
- Input: (30, 30, 3)
- Layers: Conv2D → Conv2D → MaxPool2D → Dropout (×2)
- Dense(256) → Dropout → Dense(43, softmax)
- Loss: categorical_crossentropy
- Optimizer: Adam

---

## 🔖 Example Class Labels
```
0 - Speed limit (20km/h)
1 - Speed limit (30km/h)
...
14 - Stop
...
42 - End no passing veh > 3.5 tons
```

---

## 🚀 Future Improvements
- 🔁 More epochs and data augmentation
- 🔍 YOLO integration for detection + classification
- 📷 Webcam real-time recognition
- 🛠️ Executable bundling (PyInstaller)
- 📂 Batch image processing

---

## 🤝 Contributing
```bash
git checkout -b feature/my-feature
git commit -m "Added new feature"
git push origin feature/my-feature
```
Then create a pull request!

---

## 📄 License
This project is licensed under the MIT License.

---

## 🙏 Acknowledgements
- GTSRB Dataset
- TensorFlow & Keras
- PyQt5
- Scikit-learn & Matplotlib
