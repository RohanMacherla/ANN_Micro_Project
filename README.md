**🩺 Liver Disease Classification using Deep Learning**
This project focuses on detecting and classifying different stages of liver disease using a deep learning model trained on medical diagnostic data. The model classifies records into five categories:
->No disease<br>
->Suspect disease<br>
->Hepatitis<br>
->Fibrosis<br>
->Cirrhosis<br>

**📌Problem Statement**
Liver diseases often progress silently and early detection can significantly improve outcomes. This project uses patient data with various blood parameters to build a multi-class classifier that predicts the category of liver condition using a neural network.<br>

📂 **Dataset**
Source: **Liver_Disease_data.csv**<br>
Features: Clinical parameters such as:<br>
Age,Sex,Alkaline Phosphatase,Alanine Aminotransferase,Aspartate Aminotransferase,Bilirubin,Cholinesterase,Cholesterol,Creatinine,Albumin,Protein,Gamma Glutamyl,Transferase<br>
Target: Category of liver condition<br>

🛠️ **Preprocessing**
**Missing Value Imputation:**
Mean/Median values were used based on skewness of distribution.<br>
**Outlier Handling:**
Handled using the Interquartile Range (IQR) method.<br>
**Encoding:**
Sex and Category columns encoded using LabelEncoder.<br>
Target labels were one-hot encoded for classification.<br>
**Normalization:**
(Optional – not applied in this version, but can be included)<br>

📊 **Exploratory Data Analysis**
->Plotted histograms and KDE plots for key features.<br>
->Used boxplots to visualize and identify outliers.<br>
->Checked distribution of categories.<br>

**🧠Model Architecture**
Implemented using Keras (TensorFlow backend):<br>
Input Layer (12 features)<br>
↓<br>
Dense(8) + ReLU + Dropout(0.2)<br>
↓<br>
Dense(16) + ReLU<br>
↓<br>
Dense(32) + ReLU<br>
↓<br>
Dense(64) + ReLU<br>
↓<br>
Dense(128) + ReLU<br>
↓<br>
Dense(5) + Softmax (for multi-class output)<br>

**🔧 Compilation:**
Optimizer: Adam<br>
Loss: Categorical Crossentropy<br>
Metric: Accuracy<br>

📉 **Callbacks:**
EarlyStopping (monitoring val_loss)<br>
ModelCheckpoint to save the best model<br>
**🧪 Evaluation**
Train Accuracy: **~97.4%**
Test Accuracy: **~97.5%**
ROC AUC Score: **~0.9968 (Multiclass AUC using OVR)**

**🚀 How to Run**
**Clone the repository:**
git clone https://github.com/RohanMacherla/ANN_Micro_Project.git<br>
cd liver-disease-classification<br>
**Install required packages:**
pip install -r requirements.txt<br>
**Run the notebook or script:**
jupyter notebook Liver_Disease_Classifier.ipynb<br>
