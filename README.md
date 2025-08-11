# Deep Learning-Based Satellite Image Segmentation for Land Cover Classification

## 📌 Overview
This project focuses on **automated satellite image segmentation** for **land cover classification** using deep learning.  
Leveraging the **DeepGlobe Land Cover Challenge** dataset, we implement and compare multiple **state-of-the-art segmentation models**, including both standard architectures and custom implementations.  

Applications of this work include:
- 🏙 Urban planning  
- 🌱 Environmental monitoring  
- 🚜 Agricultural management  

---

## 📂 Dataset
**Source:** [DeepGlobe Land Cover Challenge (Kaggle)](https://www.kaggle.com/datasets/balraj98/deepglobe-land-cover-classification-dataset)  

### Structure
- **Train folder**: Contains satellite images (`.jpg`) and their corresponding segmentation masks (`.png`).
- **Masks**: Encoded with a predefined RGB color scheme representing **7 land cover classes**.

### Preprocessing
- **Data Splitting**: 80% training, 20% validation.
- **Label Encoding**: RGB mask → class indices.
- **Augmentation**: Random flips and rotations.
- **Normalization**: Standard mean & standard deviation normalization.

---

## 🧠 Models Implemented
We experimented with the following models:

1. **FPN (Feature Pyramid Network)** – Multi-scale feature extraction for objects of varying sizes.
2. **DeepLabV3+** – Encoder-decoder structure with Atrous Spatial Pyramid Pooling (ASPP).
3. **U-Net** – Encoder-decoder with skip connections.
4. **U-Net++** – Nested skip connections for improved semantic fusion.
5. **Vision Transformer (ViT) for Segmentation** – Attention-based global context modeling.
6. **Custom DeepLabV3+ (from scratch)** – Implemented with a ResNet101 backbone and optimized for satellite imagery.

---

## 📊 Experimental Results

| Model               | Dice Loss | mIoU  | Pixel Accuracy |
|---------------------|----------:|------:|---------------:|
| FPN                 | 0.34      | 0.64  | 87.31%         |
| DeepLabV3+          | 0.36      | 0.65  | 87.94%         |
| U-Net               | 0.39      | 0.58  | 86.90%         |
| U-Net++             | 0.37      | 0.59  | 87.05%         |
| Custom DeepLabV3+   | 0.36      | **0.66**  | **87.56%**    |

**Key Insights:**
- Custom DeepLabV3+ achieved the best **mIoU** and competitive accuracy.
- U-Net++ performed better than U-Net due to nested skip connections.
- FPN showed strong results due to its multi-scale feature extraction.

---

## 📈 Conclusion
- CNN-based architectures like **U-Net** and **DeepLabV3+** remain highly effective for satellite imagery segmentation.
- Custom modifications can yield **incremental performance gains**.
- Future improvements may include **hyperparameter tuning**, **ensemble methods**, or **multi-modal data integration**.

---

## 👥 Contributors
- **Gaurav Manish** – Implemented U-Net & U-Net++, report writing.
- **Arjun Bhattad** – Implemented FPN & Custom DeepLabV3+, report writing.
- **Raunak Singh** – Implemented DeepLabV3+, Custom DeepLabV3+, report writing.

---


# Evaluate a model
python evaluate.py --model unet
