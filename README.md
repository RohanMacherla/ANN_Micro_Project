**🩺 Liver Disease Classification using Deep Learning**
This project focuses on detecting and classifying different stages of liver disease using a deep learning model trained on medical diagnostic data. The model classifies records into five categories:
->No disease
->Suspect disease
->Hepatitis
->Fibrosis
->Cirrhosis

📌** Problem Statement**
Liver diseases often progress silently and early detection can significantly improve outcomes. This project uses patient data with various blood parameters to build a multi-class classifier that predicts the category of liver condition using a neural network.

📂 **Dataset**
Source: **Liver_Disease_data.csv**
Features: Clinical parameters such as:
Age,Sex,Alkaline Phosphatase,Alanine Aminotransferase,Aspartate Aminotransferase,Bilirubin,Cholinesterase,Cholesterol,Creatinine,Albumin,Protein,Gamma Glutamyl,Transferase
Target: Category of liver condition

🛠️ **Preprocessing**
**Missing Value Imputation:**
Mean/Median values were used based on skewness of distribution.
**Outlier Handling:**
Handled using the Interquartile Range (IQR) method.
**Encoding:**
Sex and Category columns encoded using LabelEncoder.
Target labels were one-hot encoded for classification.
**Normalization:**
(Optional – not applied in this version, but can be included)

📊 **Exploratory Data Analysis**
->Plotted histograms and KDE plots for key features.
->Used boxplots to visualize and identify outliers.
->Checked distribution of categories.

🧠** Model Architecture**
Implemented using Keras (TensorFlow backend):
Input Layer (12 features)
↓
Dense(8) + ReLU + Dropout(0.2)
↓
Dense(16) + ReLU
↓
Dense(32) + ReLU
↓
Dense(64) + ReLU
↓
Dense(128) + ReLU
↓
Dense(5) + Softmax (for multi-class output)

🔧** Compilation:**
Optimizer: Adam
Loss: Categorical Crossentropy
Metric: Accuracy

📉 **Callbacks:**
EarlyStopping (monitoring val_loss)
ModelCheckpoint to save the best model

**🧪 Evaluation**
Train Accuracy: **~97.4%**
Test Accuracy: **~97.5%**
ROC AUC Score: **~0.9968 (Multiclass AUC using OVR)**

**🚀 How to Run**
**Clone the repository:**
git clone https://github.com/your-username/liver-disease-classification.git
cd liver-disease-classification
**Install required packages:**
pip install -r requirements.txt
**Run the notebook or script:**
jupyter notebook Liver_Disease_Classifier.ipynb
