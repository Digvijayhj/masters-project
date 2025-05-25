# Project Title: Intrusion Detection System using Phi-2

## Overview

This project implements an intrusion detection system (IDS) using the Microsoft Phi-2 model, a state-of-the-art language model, to classify network connections as either "normal" or "attack." The system is trained and evaluated on the KDD Cup '99 dataset.

## Table of Contents

1.  [Project Description](#project-description)
2.  [Key Features](#key-features)
3.  [Technologies Used](#technologies-used)
4.  [Setup Instructions](#setup-instructions)
5.  [Dataset](#dataset)
6.  [Model Architecture](#model-architecture)
7.  [Training Details](#training-details)
8.  [Evaluation Metrics](#evaluation-metrics)
9.  [Usage](#usage)
10. [Contributing](#contributing)
11. [License](#license)
12. [Contact](#contact)

## 1. Project Description

This project leverages the Phi-2 model's ability to understand and process sequential data to identify malicious network traffic. By converting network connection features into a textual format, the model can effectively learn patterns indicative of attacks. This approach offers a novel way to apply advanced language models to network security.

## 2. Key Features

* **Binary Classification:** Classifies network connections as either "normal" or "attack."
* **Customizable Training:** Allows for adjustment of hyperparameters such as epochs, batch size, and learning rate.
* **Performance Optimization:** Includes options for using mixed precision training (BF16/FP16), gradient accumulation, and gradient checkpointing to maximize efficiency on available hardware (especially GPUs).
* **Detailed Evaluation:** Provides comprehensive evaluation metrics, including accuracy, precision, recall, F1-score, and confusion matrix visualization.
* **Feature Importance Analysis:** (Optional) Implements methods to analyze the impact of individual network features on the model's predictions.
* **Inference Pipeline:** Includes an example of how to use the trained model for real-time or batch inference.

## 3. Technologies Used

* Python
* PyTorch
* Transformers
* Datasets
* Scikit-learn
* Pandas
* Evaluate
* Matplotlib, Seaborn
* CUDA

## 4. Setup Instructions

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd <repository_name>
    ```

2.  **Install the required libraries:**

    ```bash
    pip install -r requirements.txt
    ```

    * It's recommended to use a virtual environment to manage dependencies.

3.  **Download the KDD Cup '99 dataset:**

    * Place the `kdd_train.csv` and `kdd_test.csv` files in the project root directory.
    * Ensure the file paths in the notebook (`TRAIN_FILE_PATH`, `TEST_FILE_PATH`) are correct.

## 5. Dataset

* KDD Cup '99: This dataset contains network traffic data labeled as either "normal" or various types of attacks. It's a widely used benchmark for intrusion detection systems.
* The dataset is loaded and preprocessed using the `datasets` library and `pandas`.
* The notebook includes options for using subsets of the data for faster experimentation.

## 6. Model Architecture

* Microsoft Phi-2: A transformer-based language model.
* The Phi-2 model is fine-tuned for sequence classification, where the input is a textual representation of network connection features, and the output is the predicted class (normal or attack).
* The `transformers` library is used to load and adapt the model.

## 7. Training Details

* **Hyperparameters:**
    * `MODEL_NAME`:  "microsoft/phi-2"
    * `NUM_EPOCHS`:  (Configurable, e.g., 2 or 3)
    * `BATCH_SIZE`:  (Configurable, depends on available GPU memory, e.g., 16)
    * `LEARNING_RATE`:  (Configurable, e.g., 2e-5 or 3e-5)
    * `MAX_SEQ_LENGTH`:  512
* **Optimization:**
    * AdamW optimizer with weight decay.
    * Linear or cosine learning rate scheduler.
    * Gradient accumulation.
    * Gradient checkpointing.
    * Mixed precision training (BF16 or FP16).
* **Loss Function:**
    * Cross-entropy loss, potentially with class weights to address class imbalance.
* **Training Arguments:**
    * The `transformers.TrainingArguments` class is used to configure the training process.

## 8. Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* ROC Curve (Optional)
* PR Curve (Optional)

## 9. Usage

1.  **Run the Jupyter Notebook (`Break Down Phi 2.ipynb`):**

    * Execute the cells sequentially to load data, preprocess it, train the model, and evaluate its performance.
    * Modify hyperparameters and training settings in the notebook as needed.

2.  **Inference:**

    * Cell 12 provides an example of using the trained model for inference on new data using the `transformers.pipeline` class.
    * Adapt the example to your specific input format.

## 10. Contributing

* Contributions to this project are welcome!
* Please follow these guidelines:
    * Fork the repository.
    * Create a new branch for your feature or bug fix.
    * Make your changes and commit them with clear, descriptive messages.
    * Submit a pull request.

## 11. License

* [MIT License]

## 12. Contact

* Name: Digvijay Hethur Jagadeesha
* Email: hjdigvijay@gmail.com