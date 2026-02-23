Here is a `README.md` for the `notebooks` folder, structured to match your main repository's documentation style while specifically covering the contents of `data_preperation.ipynb` and `basic_MLP_accuracy.ipynb`.

---

# Notebooks: Data Preparation & Baseline Modeling

## Overview

This directory contains the core technical implementation for the **BotaniScan** plant identification tool. These notebooks cover the transition from raw scraped images to a functional baseline Multilayer Perceptron (MLP) model.

## Contents

The following notebooks are stored in this folder:

* **`data_preparation.ipynb`**: Handles the ingestion, cleaning, and preprocessing of the plant image dataset.
* **`basic_MLP_accuracy.ipynb`**: Focuses on building and evaluating the initial baseline neural network to establish a performance benchmark.

---

## [Data Preparation Process](data_preparation.ipynb)

The `data_preparation.ipynb` notebook follows a structured pipeline to ensure the dataset is ready for machine learning:

1. **Dataset Loading**: Loads images for six specific indoor plant classes: Cactus, Calathea, Monstera Minima, Peperomia, Pilea Peperomioides, and Pothos.
2. **Label Encoding**: Implements `LabelEncoder()` to convert categorical plant names into numerical labels for the model.
3. **Image Validation & Formatting**:
* Ensures all images are in **RGB** format (converting RGBA where necessary).
* Balances the dataset to approximately **200 images per class** to prevent model bias.


4. **Preprocessing**: Includes resizing images (128x128 pixels) and converting them into NumPy arrays for training.

---

## [Baseline Model Development](basic_MLP_accuracy.ipynb)
)

The `basic_MLP_accuracy.ipynb` notebook establishes the initial technical framework for identification:

* **Architecture**: A Sequential Multilayer Perceptron (MLP) built with Keras, featuring:
* A **Flatten** input layer (processing 49,152 features from 128x128x3 images).
* Five **Dense** hidden layers with **ReLU** activation (512, 512, 256, 256, and 128 units).
* A **Softmax** output layer for 6-class classification.


* **Training Strategy**:
* Uses the **Adam** optimizer and **Categorical Crossentropy** loss.
* Implements **Early Stopping** (monitoring validation loss) to prevent overfitting.


* **Performance Metrics**: Establish baseline test loss and accuracy to inform further iterations (e.g., Task 3.2 and beyond).

---

## Usage

To reproduce the results, ensure you run the notebooks in order:

1. Run `data_preparation.ipynb` to generate the processed image arrays.
2. Run `basic_MLP_accuracy.ipynb` to train the baseline model using the prepared data.