# Aerial Country Flags Detection and Classification

## Overview
This project demonstrates a pipeline for detecting country flags from aerial views using a YOLO pre-trained model. The model is trained in multiple stages using a combination of synthetic datasets generated through Python and Blender, and real-life flag images. The final model can effectively detect flags placed on the ground from a drone's perspective.

## Pipeline

The pipeline for detecting country flags consists of the following stages:
![image](https://github.com/user-attachments/assets/0450d79e-626c-4f0e-bc1a-981887ca8c4c)


1. **Pre-training**:
   - A synthetic dataset is generated using Python scripts to simulate the flags in a variety of environments and lighting conditions.
   - The YOLO pre-trained model is used to train on this synthetic dataset, providing an initial understanding of flag detection.

2. **Intermediate Training**:
   - After the initial training, we leveraged transfer learning by retraining the model on the real dataset collected from RoboFlow. This step fine-tuned the model, enabling it to adapt to the variations present in real-world images.
   
3. **Fine-tuning**:
   - A synthetic dataset is created using Blender, which simulates the flags from various angles and lighting conditions that may be encountered by drones in aerial footage.
   - The model is fine-tuned on this dataset to enhance its performance for the specific task of detecting flags in aerial views.

4. **Final Model**:
   - The final model is achieved after these stages of training and fine-tuning, resulting in a highly accurate detection system for country flags.

## Synthetic Dataset Generation (Blender)

The synthetic dataset is generated using Blender to create realistic 3D environments where flags are placed on the ground. This dataset is crucial for training the model to detect flags in various conditions such as different lighting, angles, and backgrounds.
### **Key Features**
- **Automated Dataset Generation**:
  - Synthetic images of 196 different flags.
  - Over 15,000 images generated with various augmentations.
  
- **Data Augmentation Techniques**:
  - **Random Positioning**: Flags are positioned randomly in the scene.
  - **Random Rotation**: Each flag is rotated at different angles to introduce variability.
  - **Random Camera Heights**: Simulated different camera angles and heights for a more diverse dataset.
  - **Random Backgrounds**: Varied and complex backgrounds to simulate real-world environments.

- **Auto-Annotation**:
  - Automated bounding box generation for object detection.
  - Annotations are formatted for training models using **YOLO**.


## Evaluation Metrics
![{027C6137-54D3-4CB3-91F9-BD00BA218686}](https://github.com/user-attachments/assets/e8c879f8-3c3d-4150-817c-33e60431e3bc)  

![{F1E60573-1C87-4EB9-9283-7003D2343E05}](https://github.com/user-attachments/assets/3bd10da3-9418-4095-902d-483df72006a2)

![confusion_matrix_normalized_50_dbf2c2dd6fec35a4b4bb](https://github.com/user-attachments/assets/c86f0a14-b4da-4886-b4c7-93c6ed82fb23)

![val_batch2_pred_50_639e1947b6fe9f7b15b9](https://github.com/user-attachments/assets/309e3503-3c31-4b8b-aecc-85c23e1f6250)



