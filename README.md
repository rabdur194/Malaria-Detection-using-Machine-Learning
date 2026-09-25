🔬 Automated Malaria Parasite Detection using Machine Learning & Deep Learning
An end-to-end computer vision framework designed to automate the identification of Plasmodium parasites in microscopic blood smear images. Developed as a Bachelor's/Master's thesis project, this repository combines custom Convolutional Neural Networks (CNNs), transfer learning, and model interpretability techniques to deliver high-accuracy, rapid diagnostic support.
📌 Executive Summary & Motivation
Malaria remains a major global public health challenge, causing hundreds of thousands of deaths annually. Traditional microscopic examination of blood smears—the gold standard for diagnosis—is time-intensive, requires experienced microscopists, and is vulnerable to human error and fatigue, especially in resource-limited settings.
Key Contributions of this Thesis:
•	Automated Pipeline: Standardized image preprocessing, segmentation, and noise reduction tailored for cell image analysis.
•	Architecture Comparison: Evaluated custom deep learning models alongside state-of-the-art Transfer Learning architectures (e.g., ResNet, MobileNet, VGG).
•	High Reliability: Achieved high Sensitivity/Recall to minimize false negatives in medical screening.
•	Model Explainability: Implemented interpretability techniques (e.g., Grad-CAM) to visualize cell regions driving model predictions for clinical transparency.
📊 Dataset Overview
•	Source: NIH / Kaggle Malaria Cell Images Dataset
•	Total Samples: 27,558 single-cell microscopic images
•	Classes: Balanced distribution between Parasitized ( ) and Uninfected ( )
•	Preprocessing: Resizing (  px), intensity normalization, and real-time data augmentation (rotations, flips, zoom) to prevent overfitting.
🏗 System Architecture
       [ Microscopic Blood Smear Image ]
                     │
                     ▼
  [ Image Preprocessing & Normalization ]
                     │
                     ▼
 [ Deep Learning Model (CNN / ResNet / VGG) ]
                     │
            ┌────────┴────────┐
            ▼                 ▼
   [ Parasitized ]      [ Uninfected ]
            │
            ▼
 [ Grad-CAM Heatmap Visualization ]


📈 Key Results & Metrics
Evaluation on an unseen test set (  holdout) yielded the following comparative results across models:
Architecture	Accuracy	Precision	Sensitivity (Recall)	F1-Score	AUC-ROC
Custom CNN	94.5%	94.2%	95.1%	0.946	0.978
MobileNetV2	95.8%	95.1%	96.4%	0.957	0.985
ResNet50 (Best)	96.7%	96.2%	97.3%	0.967	0.991
Note: High Sensitivity (Recall) is prioritized to ensure infected cells are rarely misclassified as healthy.
🔍 Model Explainability (Grad-CAM)
To build trust for clinical adoption, Grad-CAM (Gradient-weighted Class Activation Mapping) is utilized to generate heatmaps showing the precise visual regions (e.g., parasite rings, trophozoites) that influenced the model's decision.
🚀 Quickstart & Installation
Prerequisites
•	Python 3.8 or higher
•	CUDA-capable GPU (recommended for training)
Setup Instructions
1.	Clone the repository:
git clone https://github.com/rabdur194/Malaria-Detection-using-Machine-Learning.git
cd Malaria-Detection-using-Machine-Learning


2.	Create and activate a virtual environment:
# Linux/macOS
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate


3.	Install dependencies:
pip install -r requirements.txt


4.	Run the Interactive Streamlit Web App:
streamlit run app.py


📁 Repository Structure
├── data/                  # Instructions & scripts to download dataset
├── notebooks/             # Jupyter notebooks for EDA, training & evaluation
│   ├── 01_eda_and_preprocessing.ipynb
│   ├── 02_model_training.ipynb
│   └── 03_evaluation_and_gradcam.ipynb
├── models/                # Saved trained model weights (.h5 / .pth)
├── src/                   # Python modular scripts
│   ├── preprocessing.py   # Data pipeline functions
│   ├── models.py          # Model architecture definitions
│   └── utils.py           # Helper metrics and visualization utilities
├── app.py                 # Streamlit web application
├── requirements.txt       # Project dependencies
├── LICENSE                # MIT License
└── README.md              # Project documentation


🤝 Citation & Reference
If you use this codebase or thesis framework in your work, please cite it as:
@thesis{rabdur2024malaria,
  author = {Abdur Rahman},
  title = {Malaria Detection using Machine Learning and Computer Vision},
  year = {2024},
  publisher = {GitHub},
  journal = {GitHub Repository},
  howpublished = {\url{https://github.com/rabdur194/Malaria-Detection-using-Machine-Learning}}
}


📜 License
Distributed under the MIT License. See LICENSE for details.

