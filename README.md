CIFAR-100 CNN Image Classification

A TensorFlow/Keras-based Convolutional Neural Network project for image classification on the CIFAR-100 dataset.

Project Overview

This project starts with a baseline CNN architecture and progressively improves it to achieve better generalization and classification performance.

The notebook includes:

CIFAR-100 dataset loading and exploration

Image visualization and label inspection

Pixel normalization

Baseline CNN model

Improved CNN (Version 2) with Dropout

Improved CNN (Version 3) with:

Data augmentation

Batch normalization

Additional convolutional layers

Dropout regularization

Global Average Pooling

Learning-rate reduction

Early stopping

Best-model checkpointing

Accuracy and loss visualization

Confusion matrix analysis

Per-class precision, recall, and F1-score

Random test-image predictions

V2 vs V3 performance comparison

Model Performance

Model

Accuracy

CNN Version 2

37.48%

CNN Version 3

55.10%

Improvement

+17.62 percentage points

Version 3 substantially improves the observed evaluation performance compared with Version 2.

Note: In the original experimental setup, x_test and y_test were supplied as validation data during V3 training. Therefore, the reported 55.10% should be understood as the evaluation result from that setup rather than as a strictly held-out, untouched final test benchmark.

Version 3 Architecture

Input (32×32×3)
      │
      ▼
Conv2D 32 → BatchNorm → Conv2D 32 → BatchNorm
      │
   MaxPool → Dropout
      │
      ▼
Conv2D 64 → BatchNorm → Conv2D 64 → BatchNorm
      │
   MaxPool → Dropout
      │
      ▼
Conv2D 128 → BatchNorm → Conv2D 128 → BatchNorm
      │
   MaxPool → Dropout
      │
      ▼
Global Average Pooling
      │
      ▼
Dense 256 → BatchNorm → Dropout
      │
      ▼
Softmax (100 classes)

Dataset

The project uses the CIFAR-100 dataset, containing 100 image classes with RGB images of size 32×32.

The dataset is loaded directly through TensorFlow/Keras.

Technologies

Python

TensorFlow / Keras

NumPy

Matplotlib

Scikit-learn

Google Colab / Jupyter Notebook

Project Structure

CIFAR-100-CNN-Image-Classification/
│
├── Project_CIFER_100.ipynb
├── README.md
├── requirements.txt
└── .gitignore

How to Run

The project can be run directly in Google Colab.

Open Project_CIFER_100.ipynb.

Run the notebook cells in order.

TensorFlow downloads the CIFAR-100 dataset automatically.

Train the baseline and improved models.

Review the performance plots and evaluation results.

Results & Analysis

The Version 3 model demonstrates a substantial improvement over Version 2. The project also includes a confusion matrix and per-class metrics to investigate where the model performs well and where classification remains challenging.

Version 3 performs strongly on classes such as road, wardrobe, sunflower, orange, and apple, while classes such as otter, squirrel, seal, lizard, and girl remain more challenging.

Future Improvements

Possible future directions include:

Using a dedicated validation split while keeping the test set completely untouched

More advanced data augmentation

Learning-rate scheduling experiments

Transfer learning with a pretrained image model

Further hyperparameter tuning

Deployment as a simple image-classification web application

Author

Muhammad Jarrar Hussain
