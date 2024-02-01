# Investigating Transfer Learning and Scratch Training for Image Recognition

## Overview
This project explores image classification using convolutional neural networks (CNNs). The goal is to classify images into three categories - apparel, chairs, and footwear.
The project covers:

- Data collection and labeling
- Splitting data into train, validation, and test sets
- Building input pipelines with data augmentation
- Fine-tuning a pretrained CNN model (ResNet50)
- Training a CNN from scratch

## Data Collection and Labeling
- Collected over 100 images per class (apparel, chairs, footwear) using a phone camera
- Labeled images and assigned category labels - 0 for apparel, 1 for chairs, 2 for footwear

<img width="950" alt="image" src="https://github.com/gaurichaudhari9/image-classification-cnn/assets/25304556/2ca49bb5-52c8-45b3-b3dc-119e6ae70705">


## Data Splitting
- Split data into 60% train, 20% validation, 20% test per class
- Copied split data into separate folders for train, validation, and test

## Input Pipeline and Data Augmentation
- Used Keras image_dataset_from_directory to load images as datasets
- Added random flips and rotations for data augmentation
- Defined a pipeline that applies these data augmentation to each element of the training data set in parallel.
- I am also using `_prefetch_` to avoid I/O blocking.

## Fine-tuning ResNet50
- Used transfer learning with pretrained ResNet50 model
- Froze base layers, added GlobalAveragePooling and Dense layers
- Achieved **98.46% test accuracy** after 5 epochs of fine-tuning

<img width="903" alt="image" src="https://github.com/gaurichaudhari9/image-classification-cnn/assets/25304556/368f5c47-9ddd-4c0b-bd51-79b38c3fcaa0">

<img width="1138" alt="image" src="https://github.com/gaurichaudhari9/image-classification-cnn/assets/25304556/6b3a9ecb-9306-4298-ae38-dcf4016a1ad3">


## Training CNN from Scratch
- Built a CNN model with convolutional, pooling, batch norm, dropout layers
- Trained for 10 epochs using Adam optimizer
- Achieved **70%** test accuracy
- Training a model from scratch on a small dataset makes it difficult to learn robust features compared to fine-tuning a pretrained model. More data would be needed to improve accuracy.

<img width="653" alt="image" src="https://github.com/gaurichaudhari9/image-classification-cnn/assets/25304556/026072da-1c90-40f0-92e4-0c5616043d96">

<img width="1121" alt="image" src="https://github.com/gaurichaudhari9/image-classification-cnn/assets/25304556/94613fbd-466d-4004-b224-01b63ea2df8a">




## Conclusion
This project demonstrated classifying images using CNNs. Fine-tuning a pretrained CNN model like ResNet50 achieved high accuracy given the small dataset size. Training a CNN from scratch produced decent but lower accuracy. Overall, the models were able to effectively classify the apparel, chair, and footwear images.

## References
- Dataset collected using a phone camera. Location: Indiana University Bloomington Campus
- Models built with TensorFlow/Keras
