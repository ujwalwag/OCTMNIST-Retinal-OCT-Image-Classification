# 🩺 OCTMNIST: Retinal OCT Image Classification with CNNs

This project explores deep learning techniques for classifying retinal OCT images using the **OCTMNIST** dataset (a subset of MedMNIST).  
The work includes preprocessing, visualization, and training convolutional neural networks (CNNs) with architectural improvements such as **Batch Normalization** and **Learning Rate Scheduling**, achieving validation accuracy above 93%.  

---

## 📊 Dataset
- **Source**: [MedMNIST – OCTMNIST](https://medmnist.com/)  
- **Size**:  
  - Training: 97,477 images  
  - Validation: 10,832 images  
  - Test: 1,000 images  
- **Image Dimensions**: 28×28×1 (grayscale)  
- **Classes (4)**:  
  - Choroidal Neovascularization  
  - Diabetic Macular Edema  
  - Drusen  
  - Normal  

- **Collection**: MedMNIST → **OCTMNIST**  
- **Samples**: Train 97,477 • Val 10,832 • Test 1,000 (28×28 grayscale, 4 classes).:contentReference[oaicite:0]{index=0}  
- **Refs**: https://medmnist.com/ • https://github.com/MedMNIST/MedMNIST • https://zenodo.org/record/6496656

### Install & get data
```bash
pip install -r requirements.txt
# or minimal:
# pip install medmnist torch torchvision torchaudio matplotlib seaborn scikit-learn torchinfo


## 🛠️ Workflow
1. **Data Loading & Preprocessing**
   - Normalized pixel values to [−1, 1].  
   - Applied PyTorch transforms for augmentation & tensor conversion.  
   - Used predefined MedMNIST splits for train/val/test.  

2. **Visualization**
   - Class distribution bar chart.  
   - Sample image grid per class.  
   - Histogram of pixel intensity distribution.  

3. **CNN Models**
   - **Base Model**: 2 Conv layers, 2 Fully Connected layers (128 hidden units), Dropout (0.5), ReLU activations.  
   - **Improved Model**: Added BatchNorm + Learning Rate Scheduler → **Validation Accuracy: 93.14%**.  

4. **Training**
   - Optimizer: Adam (lr=0.001 → 0.0001 with scheduler).  
   - Loss: CrossEntropyLoss.  
   - Epochs: 30.  
   - Best base model Val Acc: 91.09%.  
   - Improved model Val Acc: 93.14%.  
   - Base Test Acc: 70.30% (generalization gap identified).  

---

## 📂 Repository Structure
├── data/ # Placeholder for OCTMNIST data(there's no dataset here)
├── notebooks/ # Jupyter notebooks for EDA & training
├── docs/ # Report
├── models/ # Saved models
├── requirements.txt # Dependencies
└── README.md # Project documentation

📄 Read the full project report [[here](https://github.com/ujwalwag/OCTMNIST-Retinal-OCT-Image-Classification/blob/main/docs/a0_part3_50560587.pdf)
