# LL-Image-Enhancement

## Overview
This repository contains a **deep learning–based low-light image enhancement** project. The work focuses on:
1. **Baseline ML Models** (Linear Regression, SVM, XGBoost) to adjust brightness/saturation.  
2. A **U-Net** convolutional neural network that learns to enhance images in a supervised manner.  
3. A **Zero-DCE** model (based on Guo et al., 2020), which estimates pixel-wise curves to iteratively improve low-light images.

All experiments are demonstrated in a **Jupyter notebook**, originally run in a Kaggle environment. Feel free to adapt it for your local environment or any cloud notebook platform.

---

## Installation
1. **Clone the repository**:
   ```bash
   git clone https://github.com/MooseML/LL-Image-Enhancement.git
   ```
2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

These steps provide the basic setup for Python libraries like TensorFlow, scikit-image, OpenCV, and others needed for training and inference.

---

## Usage
1. **Notebook Execution**  
   - Open the `.ipynb` notebook in a Jupyter environment (e.g., Kaggle, Google Colab, or local JupyterLab).  
   - Run the cells in order to reproduce data loading, EDA, baseline ML model training, U-Net training/tuning, and Zero-DCE training.  

2. **Data Preparation**  
   - By default, the code uses the **LOw-Light (LOL) dataset** that is linked in the data folder. Make sure you have paths set correctly to low-light and ground-truth images.  
   - You can substitute or add your own images by updating the relevant file paths.

3. **Training & Evaluation**  
   - **Baseline ML Models**: Feature extraction for brightness, contrast, saturation. Then train and apply them to predict global adjustments.  
   - **U-Net**: Uses an encoder–decoder structure with skip connections and includes **Perceptual Loss** with a pretrained VGG network for enhanced visuals.  
   - **Zero-DCE**: A lightweight CNN for iteratively refining low-light images. Includes custom losses for color consistency, spatial consistency, exposure, and total variation.

---

## Notes on Environment
- Originally tested in a **Kaggle** environment (Linux with Python 3.10.12, GPU runtime enabled for the deep learning models).  
- If running locally, ensure you have a supported **GPU** (NVIDIA) with CUDA drivers installed for faster training.  
- The **`requirements.txt`** file in the repository should help replicate the library versions.

---

## References (Selected)
- **Guo, C., Li, C., Guo, J., Loy, C. C., Hou, J., Kwong, S., & Cong, R.** (2020). Zero-Reference Deep Curve Estimation for Low-Light Image Enhancement. In *2020 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)* (pp. 1777–1786). IEEE.  
- **Wei, C., Wang, W., Yang, W., & Liu, J.** (2018). Deep Retinex Decomposition for Low-Light Enhancement. *arXiv preprint arXiv:1808.04560*.  
- **LOL Dataset**: [https://drive.google.com/file/d/157bjO1_cFuSd0HWDUuAmcHRJDVyWpOxB/view](https://drive.google.com/file/d/157bjO1_cFuSd0HWDUuAmcHRJDVyWpOxB/view)  
- **Keras: Zero-DCE Example**: [https://keras.io/examples/vision/zero_dce/](https://keras.io/examples/vision/zero_dce/)  

For all references and details, see the corresponding sections in the notebook.
