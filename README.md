# Brain-tumour-detection
This project implements an advanced Brain Tumour Detection system using the YOLOv8 object detection framework. It accurately localises and classifies four distinct states within MRI scans: Glioma, Meningioma, Pituitary tumours, and No Tumour. The model is trained on a comprehensive dataset featuring bounding box annotations to provide precise, real-time diagnostic support.

## 🌟 Key Features
- Multi-Class Detection: The model is trained to identify four specific classes: Glioma, Meningioma, Pituitary, and No Tumour (classification).

- Precise Localisation: Utilises YOLOv8's bounding box capabilities to accurately pinpoint the tumour location within the MRI scan.

- Efficient Training: Leveraging the ultralytics library for fast and efficient training and inference.

- End-to-End Workflow: Includes steps for data import, preparation, model training, and visualisation of results.

## ⚙️ Technologies and Libraries
The core of this project relies on the "ultralytics" package for the YOLOv8 implementation, complemented by standard Python data science tools.

- Object Detection:	ultralytics
- Data Handling:	kagglehub, os, shutil
- Visualisation/Utility:	matplotlib.pyplot, numpy, pandas
- mage Processing:	cv2 (OpenCV)

## 📁 Dataset
The model is trained on an MRI dataset specifically prepared with bounding box annotations for tumour localisation.

Source: https://www.kaggle.com/datasets/ahmedsorour1/mri-for-brain-tumor-with-bounding-boxes

