# Thesis: Deep Learning and xAI applied to TB Screening

## Overview
This folder contains my thesis work, which explores custom CNNs and pre-trained CNNs in the domain of TB screening using small (704 chest x-rays) and moderately large (4200 chest-xrays) datasets. Grad-CAM is used to validate the results of the models.

The full log of the project, including experiment runs, hyperparameter details, and results are in the google sheet below (comment access is given):

[![Experiment Results](https://img.shields.io/badge/Experiment_Results-Google_Sheets-34A853?logo=google-sheets&logoColor=white)](https://docs.google.com/spreadsheets/d/1yfOcmW0lD8mNYdcBe97ekJ9IfUImScAMzi2XEnvoDVU/edit?gid=405324248#gid=405324248)

*Note: If a notebook fails to render on GitHub, please use the "Open in Colab" badges in the link column to view and run the code directly.*

## 📂 Classification

| Notebook Name | Description | Link |
| :--- | :--- | :--- |
| **Classification Custom CNNs** | Training custom CNN models for classification. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Classification/Classification_Custom_CNNs.ipynb) |
| **Classification Segmented Lungs** | Training custom CNN models on segmented lung images. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Classification/Classification_Segmented_Lungs_Custom_CNN.ipynb) |
| **DenseNet169** | Transfer learning experiments using DenseNet169. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Classification/DenseNet169.ipynb) |
| **EfficientNet B3** | Transfer learning experiments using EfficientNet B3. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Classification/EfficientNet_B3.ipynb) |
| **ResNet50** | Transfer learning experiments using ResNet50. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Classification/ResNet50.ipynb) |
| **VGG 16** | Transfer learning experiments using VGG 16. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Classification/VGG_16.ipynb) |

## 📂 Segmentation

| Notebook Name | Description | Link |
| :--- | :--- | :--- |
| **Segmentation Custom CNN** | Custom CNN architecture for lung segmentation. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Segmentation/Segmentation_Custom_CNN.ipynb) |
| **Segmentation Inference** | Running inference and generating lung masks using trained models. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Segmentation/Segmentation_Inference.ipynb) |
| **Segmentation Unet Full** | Full implementation of U-Net for lung segmentation. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi232/MSc_Data_Science/blob/main/Thesis/Segmentation/Segmentation_Unet_Full.ipynb) |

---
