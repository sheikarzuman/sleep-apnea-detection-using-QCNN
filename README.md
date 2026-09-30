🫀 Sleep Apnea Detection Using Hybrid QCNN

A hybrid quantum-classical machine learning approach for detecting sleep apnea from ECG signals using a Quantum Convolutional Neural Network (QCNN) and classical machine learning models.

The project combines classical preprocessing, dimensionality reduction, quantum feature extraction, and ensemble learning to identify patterns in ECG signals associated with sleep apnea.

Project: Hybrid QCNN Model for Sleep Apnea Detection Using ECG Signals
Institution: VIT Chennai
Authors: Swetha Selvakumaran, Shaik Nadeem Ansari, Sheik Arzuman S

⸻

📌 Overview

Sleep apnea is a sleep disorder characterized by repeated interruptions in breathing during sleep. Detecting these events from physiological signals such as ECG can help support automated screening and analysis.

This project explores whether quantum-enhanced feature extraction can be combined with classical machine learning to improve sleep apnea classification.

The proposed pipeline is:

ECG Dataset
     ↓
Data Sampling
     ↓
Label Encoding
     ↓
Feature Standardization
     ↓
PCA Dimensionality Reduction
     ↓
Quantum Feature Embedding
     ↓
QCNN Quantum Circuit
     ↓
Quantum-Enhanced Features
     ↓
Classical ML Models
     ↓
Ensemble Prediction
     ↓
Sleep Apnea Classification

The dataset is randomly sampled to 10% for computational efficiency, followed by standardization and PCA reduction to 10 components.

⸻

⚛️ Why Quantum Machine Learning?

ECG datasets can contain a large number of features and complex relationships between physiological measurements.

The project investigates the use of quantum circuits to transform these features into a quantum-enhanced representation before classification.

The QCNN circuit uses:

* Amplitude Embedding to encode classical features into a quantum state
* Hadamard gates to introduce superposition
* CNOT gates to introduce entanglement
* RZ and RY rotation gates for feature-dependent transformations
* Pauli-Z measurements to convert the quantum state back into classical features

The resulting expectation values form the quantum-enhanced feature vector used by the downstream classifiers.

⸻

🧠 Methodology

1. Dataset

The project uses an ECG sleep apnea dataset stored as:

ecg_sleep_apnea_dataset.csv

The target variable is:

Target

For computational efficiency, 10% of the dataset is sampled using a fixed random state.

⸻

2. Data Preprocessing

The preprocessing pipeline consists of:

Label Encoding

Converts the target classes into numerical labels.

Standardization

StandardScaler is used to normalize the input features to zero mean and unit variance.

Principal Component Analysis

PCA reduces the feature space to:

10 principal components

This makes the data more manageable for the quantum circuit while retaining the most significant information from the original feature space.

⸻

3. Quantum Feature Extraction

The reduced feature vector is passed into a PennyLane quantum circuit.

qml.AmplitudeEmbedding(
    features=inputs,
    wires=range(n_qubits),
    pad_with=0,
    normalize=True
)

The circuit then applies quantum operations including:

Hadamard
CNOT
RZ
RY

Finally, the circuit measures the expectation value of the Pauli-Z operator for each qubit.

These measurements form the quantum-enhanced feature representation.

⸻

🧬 QCNN Architecture

The architecture can be summarized as:

              ECG Features
                   │
                   ▼
             StandardScaler
                   │
                   ▼
                  PCA
             10 Components
                   │
                   ▼
          Amplitude Embedding
                   │
                   ▼
        ┌─────────────────────┐
        │   Quantum Circuit   │
        │                     │
        │   Hadamard          │
        │   CNOT              │
        │   RZ / RY           │
        └─────────────────────┘
                   │
                   ▼
          Pauli-Z Measurements
                   │
                   ▼
      Quantum-Enhanced Features
                   │
        ┌──────────┼──────────┐
        ▼          ▼          ▼
       SVM    Random Forest   GBM
        │          │          │
        └──────────┼──────────┘
                   ▼
             Ensemble Model
                   │
                   ▼
        Sleep Apnea Prediction

The QCNN architecture is designed as a hybrid quantum-classical pipeline where quantum feature extraction is followed by classical classification.

⸻

🤖 Machine Learning Models

The project experiments with multiple classical models using the quantum-enhanced features:

* Support Vector Machine (SVM)
* Random Forest
* Gradient Boosting
* Deep Neural Network (DNN)
* Ensemble-based classification

Hyperparameter optimization is performed using GridSearchCV and RandomizedSearchCV in different experimental stages.

⸻

📊 Results

The project report reports the following final performance:

Model	Accuracy
SVM with Quantum Features	91.15%
Random Forest with Quantum Features	96.10%
Final Ensemble	96.30%

The reported final ensemble accuracy is 96.30% on the evaluated test set.

The project also compares the proposed approach against a standalone classical CNN, with the report documenting 87.7% accuracy for the CNN and 93.3% for an earlier ensemble configuration. These figures come from different experimental stages, so they should not be interpreted as a single controlled benchmark.

⸻

🛠️ Technologies Used

Programming

* Python

Quantum Computing

* PennyLane

Machine Learning

* Scikit-learn
* TensorFlow / Keras

Data Processing

* Pandas
* NumPy
* StandardScaler
* PCA

Visualization

* Matplotlib
* Seaborn

Environment

* Google Colab
* Python 3

⸻

🚀 Getting Started

1. Clone the repository

git clone https://github.com/sheikarzuman/sleep-apnea-detection-using-QCNN.git
cd sleep-apnea-detection-using-QCNN

2. Install dependencies

pip install pandas numpy matplotlib seaborn scikit-learn pennylane tensorflow

PennyLane is required for executing the quantum circuits used in the project. The original notebook installs PennyLane before defining the quantum device and circuit.

3. Add the dataset

Place the dataset in the working directory:

ecg_sleep_apnea_dataset.csv

4. Run the notebook

The project is designed to run in Google Colab.

Open:

sleep apnea detection qcnn

and execute the notebook cells sequentially.

⸻

📁 Project Structure

sleep-apnea-detection-using-QCNN/
│
├── sleep apnea detection qcnn
├── ecg_sleep_apnea_dataset.csv
└── README.md

The dataset may need to be obtained separately depending on its distribution and licensing.

⸻

🔬 Key Features

* ECG-based sleep apnea classification
* Classical preprocessing pipeline
* PCA-based dimensionality reduction
* Quantum amplitude embedding
* Quantum feature extraction
* QCNN-inspired quantum circuit
* Hybrid quantum-classical architecture
* Multiple classical classifiers
* Hyperparameter optimization
* Ensemble-based prediction

⸻

⚠️ Limitations

This project is a research and academic prototype rather than a clinical diagnostic system.

Some important limitations include:

* Only a 10% sample of the dataset is used in the implementation for computational efficiency.
* The quantum circuit is simulated using PennyLane’s default.qubit device rather than executed on physical quantum hardware.
* Quantum circuit simulation becomes increasingly computationally expensive as the number of qubits grows.
* Real quantum hardware introduces noise and error-related challenges.
* Further optimization and validation would be required before considering real-world clinical applications.

⸻

🔮 Future Work

Potential extensions include:

* Testing on the complete ECG dataset
* More extensive hyperparameter optimization
* Improved quantum circuit architectures
* Testing on real quantum hardware
* Noise-aware quantum circuit design
* Advanced ECG feature engineering
* Larger and more diverse datasets
* Cross-dataset validation
* Development of a real-time ECG monitoring system

⸻

📚 Project Documentation

This repository is based on the academic project:

“Hybrid QCNN Model for Sleep Apnea Detection Using ECG Signals”

The project investigates the intersection of:

Quantum Computing
        +
Machine Learning
        +
Biomedical Signal Processing
        =
Sleep Apnea Detection

