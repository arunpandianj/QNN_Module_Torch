# 🧠 QNN Module with PyTorch

### *Hybrid Classical--Quantum Neural Network using PennyLane & PyTorch*

This repository contains a Colab notebook **`qnn_module_torch.ipynb`**
demonstrating how to combine **quantum circuits** with **PyTorch neural
networks** to build hybrid machine learning models.\
The example uses **PennyLane's TorchLayer** to convert a quantum node
(QNode) into a trainable PyTorch layer.

------------------------------------------------------------------------

## 🚀 **Repository Structure**

    qnn_module_torch/
    │
    ├── qnn_module_torch.ipynb   # Main notebook with full implementation
    ├── README.md                # Documentation (this file)
    └── images/                  # (Optional) Store screenshots, plots, diagrams

------------------------------------------------------------------------

## 🎯 **Objective**

To demonstrate how to:

-   Build a **hybrid model** combining classical linear layers and
    quantum circuits\
-   Encode data using **AngleEmbedding**\
-   Introduce entanglement using **BasicEntanglerLayers**\
-   Train quantum + classical parameters end-to-end using PyTorch\
-   Classify a nonlinear dataset (e.g., `make_circles` or `make_moons`)

------------------------------------------------------------------------

## 🧩 **Key Concepts Covered**

### ✔ **Angle Embedding**

Encodes classical features into quantum states through rotational gates.

### ✔ **Entanglement Layers**

`BasicEntanglerLayers` allow qubits to interact and learn correlated
patterns.

### ✔ **TorchLayer Integration**

Converts a QNode into a fully trainable PyTorch-compatible layer.

### ✔ **Hybrid Model Architecture**

Example hybrid model includes:

1.  Classical Linear Layer\
2.  Quantum Layer (QNode → TorchLayer)\
3.  Classical Linear Layer\
4.  Softmax Layer

------------------------------------------------------------------------

## 📘 **Notebook Contents**

The notebook **qnn_module_torch.ipynb** includes:

### **1. Dataset Preparation**

-   Using `sklearn.datasets.make_circles`
-   Visualizing data\
-   Converting labels to one-hot vectors

### **2. Defining the Quantum Node (QNode)**

-   2-qubit quantum circuit\
-   AngleEmbedding for input\
-   Entanglement block with trainable weights\
-   Measurement using Hadamard expectation values

### **3. Converting QNode → TorchLayer**

-   Specifying weight shapes\
-   Creating `qlayer = TorchLayer(qnode, weight_shapes)`

### **4. Building the Hybrid Model Using PyTorch Sequential**

``` python
model = torch.nn.Sequential(
    clayer_1,
    qlayer,
    clayer_2,
    softmax
)
```

### **5. Training the Hybrid Model**

-   Optimizer: SGD\
-   Loss: L1Loss\
-   Training loop with DataLoader

### **6. Accuracy Evaluation and Plotting Results**

### **7. Custom Hybrid Model (Non-Sequential)**

A more advanced architecture combining: - Classical expansion layer\
- Two separate quantum layers\
- Concatenation\
- Final classical layer

------------------------------------------------------------------------

## ⚙️ **Installation**

Install dependencies using pip:

``` bash
pip install pennylane torch matplotlib scikit-learn
```

Or inside Google Colab:

``` python
!pip install pennylane
```

------------------------------------------------------------------------

## ▶️ **Running the Notebook**

1.  Upload `qnn_module_torch.ipynb` to Google Colab **or** run it
    locally.\
2.  Execute each cell sequentially.\
3.  Train the hybrid quantum--classical model.\
4.  Observe the loss reduction and classification accuracy.

------------------------------------------------------------------------

## 📊 **Results**

Typical results include:

-   Smooth convergence over multiple epochs\
-   High accuracy (\>85%) on nonlinear datasets\
-   Demonstration of improved feature representation from quantum
    embeddings

------------------------------------------------------------------------

## 📚 **Learning Tasks (for Students)**

Suggested tasks include:

-   Modify the entanglement pattern\
-   Change number of qubits\
-   Replace `make_circles` with `make_moons`\
-   Try different optimizers (Adam, RMSProp)\
-   Increase quantum layer depth\
-   Visualize decision boundaries

------------------------------------------------------------------------

## 🛠️ **Technologies Used**

  Technology         Purpose
  ------------------ -------------------------------------
  **PennyLane**      Quantum simulation & quantum layers
  **PyTorch**        Deep learning framework
  **scikit-learn**   Dataset generation
  **matplotlib**     Visualization
  **NumPy**          Numerical processing

------------------------------------------------------------------------

## 📎 **References**

1.  PennyLane Documentation\
2.  TorchLayer API\
3.  PyTorch Documentation

------------------------------------------------------------------------

## 🧑‍💻 **Author**

Dr. Arun Pandian J\
Assistant Professor Senior Grade-I\
School of Computer Science Engineering and Information Systems\
Vellore Institute of Technology, Vellore
