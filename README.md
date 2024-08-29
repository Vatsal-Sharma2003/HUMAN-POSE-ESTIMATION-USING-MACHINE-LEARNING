# Human Action Recognition using Pose Estimation and Object Recognition

This repository contains the implementation of a human action recognition system that integrates human pose estimation and object recognition. The project leverages pre-trained deep learning models MoveNet and MobileNetV3 to enhance the accuracy and robustness of action recognition tasks.

## Overview

The objective of this project is to create a hybrid system that combines the spatial information from human pose estimation with the contextual understanding provided by object recognition. By doing so, the system is capable of interpreting complex human activities more effectively.

## Project Structure

- **Dataset**: The Human Action Recognition (HAR) Dataset from Kaggle, containing 12,600 labeled images across 15 action classes.
- **Feature Extraction**:
  - **Human Pose Estimation**: Utilizing Google's MoveNet for detecting keypoints on the human body.
  - **Object Recognition**: Using MobileNetV3 to identify objects in the environment.
- **Feature Vector**: The final feature vector combines the output of the pose estimation and object recognition models, resulting in a lightweight representation of each image.
- **Classification Methods**:
  - Support Vector Machine (SVM)
  - Random Forest (RF)
  - Neural Network (NN)
  
## Implementation Details

### MoveNet - Human Pose Estimation

MoveNet is a convolutional neural network optimized for detecting human keypoints with high accuracy and speed. It is pre-trained on datasets like COCO and Google-Active, providing two variants: MoveNet Lightning (faster, for real-time applications) and MoveNet Thunder (more accurate, for applications requiring higher precision).

### MobileNetV3 - Object Recognition

MobileNetV3 is designed for object recognition, optimized for mobile and embedded devices. It employs techniques like Depthwise Separable Convolutions and Squeeze-and-Excitation blocks, making it efficient yet powerful for recognizing a wide variety of objects.

### Feature Vector

The final feature vector consists of:
- Flattened human pose keypoints (17 keypoints, each with 3 coordinates).
- A 100-dimensional vectorized representation of the top 5 detected objects.

This 151-dimensional vector is used as input for the classification models.

## Results

The experiments revealed that the integration of human pose and object data significantly improves classification accuracy. The best performance was achieved using an SVM classifier with the combined feature vector from MoveNet Thunder and MobileNetV3 Large.

### Performance Summary

- **Best Accuracy**: 57.1% using SVM with MoveNet Thunder and MobileNetV3 Large.
- **Feature Importance**: Both pose and object features contribute significantly to the classification performance, with an average improvement of over 12% when using both.

## Conclusion

This project demonstrates the potential of combining pose estimation and object recognition for human action recognition tasks. The multimodal approach significantly enhances accuracy, particularly in complex scenes with varied environments.

## Authors

- Lorenzo Barbiero
- Alessio Pitteri
