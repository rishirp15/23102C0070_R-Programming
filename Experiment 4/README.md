# Image Recognition & Classification with Keras in R

**Name:** Rishi Raj Phadale
**Roll No.:** 23102C0070
**Course:** R Programming
**Lab:** Experiment 4 – R Project Implementation and Version Control Using GitHub

---

## 📌 Project Objective

The objective of this project is to implement a complete, end-to-end image classification pipeline in R using the `keras` and `EBImage` packages. The project demonstrates how R can be used not just for statistical analysis but for deep learning tasks — reading raw image data, preprocessing it into a numeric tensor format, building and training a neural network, and evaluating its predictions — following the workflow demonstrated in the prescribed reference video.

## 📝 Problem Description

Given a small set of labeled images belonging to two classes (referred to here as **"p"** images and **"c"** images), the task is to train a fully-connected neural network that can correctly classify an unseen test image into its correct class. This involves:

- Reading images from disk into R.
- Resizing and reshaping them into a fixed-size numeric array suitable for a neural network.
- Splitting the data into training and test sets.
- One-hot encoding the class labels.
- Building, compiling, and training a Keras sequential model.
- Evaluating the trained model and generating predictions on the data.

## 📂 Dataset Information

- **Type:** Custom image dataset (12 images total, stored locally in an `images/` folder).
- **Classes:** 2 classes — 6 images per class (`p1.jpg`–`p6.jpg` and `c1.jpg`–`c6.jpg`).
- **Split:** 10 images used for training (5 from each class), 2 images held out for testing (1 from each class).
- **Preprocessing:** Every image is resized to **28 × 28 pixels** with 3 color channels (RGB) and reshaped into a flat vector of length `28 × 28 × 3 = 2352` before being fed into the network.

> Note: The raw image files are included in the `images/` folder of this repository. If you wish to reproduce the project with your own images, replace the files in `images/` with your own, keeping the same naming convention and class balance.

## 📦 R Packages / Libraries Used

| Package | Purpose |
|---|---|
| `EBImage` (Bioconductor) | Reading, resizing, and reshaping image data |
| `keras` | Building, compiling, training, and evaluating the neural network |
| `BiocManager` | Installing `EBImage` from Bioconductor |

## ⚙️ Major Operations Performed

1. **Environment Setup** – Installed system dependencies, `EBImage` via Bioconductor, and `keras` (with its TensorFlow backend via `install_keras()`).
2. **Image Import** – Read all 12 `.jpg` images from the `images/` directory using `readImage()`.
3. **Resize & Reshape** – Resized every image to 28×28 and reshaped it into a 3-channel array using `resize()` and `array_reshape()`.
4. **Train/Test Split** – Combined 10 images into a training matrix (`trainx`) and 2 images into a test matrix (`testx`); assigned corresponding class labels (`trainy`, `testy`).
5. **One-Hot Encoding** – Converted numeric class labels into categorical (one-hot) format using `to_categorical()`.
6. **Model Building** – Built a sequential fully-connected neural network with two hidden `relu` layers (256 and 128 units) and a `softmax` output layer for 2-class classification.
7. **Model Compilation** – Compiled the model with `categorical_crossentropy` loss, the `rmsprop` optimizer, and `accuracy` as the evaluation metric.
8. **Model Training** – Trained the model for 30 epochs with a batch size of 32 and a 20% validation split.
9. **Evaluation & Prediction** – Evaluated the trained model on the training data and generated class predictions, comparing predicted vs. actual labels in a confusion table.

## ▶️ Instructions to Execute the Project

1. Clone this repository:
   ```bash
   git clone https://github.com/rishirp15/23102C0070_R-Programming
   cd Experiment 4
   ```
2. Open `RProg_Experiment_4_23102C0070.ipynb` in **Google Colab** (recommended, since it installs system-level dependencies) or in **RStudio / Jupyter with an R kernel**.
3. Ensure the `images/` folder (containing `p1.jpg`–`p6.jpg` and `c1.jpg`–`c6.jpg`) is present in the working directory.
4. Run the notebook cells in order, starting from **Section 1: Setup in Colab**, which installs `EBImage`, `keras`, and the TensorFlow backend.
5. Continue running each subsequent section (Read images → Resize & reshape → Train/test split → One-hot encoding → Model → Compile → Fit → Evaluate & Predict) in sequence.
6. Review the printed model summary, training history, evaluation metrics, and the final prediction table.

## 📊 Important Results / Output

- The model architecture consists of an input layer (2352 features), two hidden dense layers (256 and 128 units, `relu` activation), and a 2-unit `softmax` output layer.
- The model was trained for 30 epochs and evaluated on the training set, reporting **loss** and **accuracy**.
- Final predictions were generated for each training image and compared against the actual class labels using a confusion table (`table(Predicted, Actual)`), along with the raw class probabilities for each image.


## 📁 Repository Structure

```
.
├── RProg_Experiment_4_23102C0070.ipynb   # Main R notebook (complete project)
├── images/                               # Dataset (12 training/test images)
└── README.md                             # Project documentation (this file)
```

## 👤 Author

**Rishi Raj Phadale** — Roll No. 23102C0070
