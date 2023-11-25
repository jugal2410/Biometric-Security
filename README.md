# Biometric Authentication using FingerprintNet

## Overview

This code implements a biometric authentication system using a pre-trained FingerprintNet model. The FingerprintNet model used is DenseNet201, a deep convolutional neural network designed for image classification tasks.

## Requirements

- Python 3.x
- TensorFlow 2.x
- OpenCV (cv2)
- NumPy
- scikit-learn

## Usage

1. **Data Preparation:**
   - Organize your dataset into two folders: one for real fingerprint images and another for altered/fake fingerprint images.
   - Update `real_dir` and `fake_dir` variables with the paths to your real and fake image folders.

2. **Data Loading and Preprocessing:**
   - The `load_data` function loads images from a specified folder and assigns labels.
   - Real and fake images are loaded separately, and their labels are set as 1 and 0, respectively.
   - Images are resized to match the input shape expected by the FingerprintNet model (96x96x3).
   - Images are preprocessed using DenseNet's `preprocess_input` function.

3. **Model Architecture:**
   - FingerprintNet (DenseNet201) is loaded with pre-trained weights from ImageNet.
   - The model is set to exclude the top classification layer to extract features.

4. **Data Splitting:**
   - The dataset is split into training and testing sets using `train_test_split`.

5. **Feature Extraction:**
   - Features are extracted from the pre-trained FingerprintNet for both training and testing sets.

6. **Training (Optional):**
   - If you intend to train a new model on top of the extracted features, you can add additional layers to the model and train it.

7. **Acknowledgments:**
   - The FingerprintNet model is based on DenseNet201, pre-trained on ImageNet.

## References

- [DenseNet201](https://www.tensorflow.org/api_docs/python/tf/keras/applications/DenseNet201)
