# Project Procedure & Module Breakdown

## Objective
Replicate the Hybrid BERT paper exactly to achieve 99%+ accuracy on the ECU-IoHT dataset.

## Module 1: Data Preprocessing (`data_loader.py`)
* **Input:** Read the `ECU_IoHT.xlsx` file.
* **Task:** Drop empty columns, handle missing values, and extract the raw packet payloads/URLs.
* **Output:** Cleaned text data and corresponding labels (0 = Benign, 1 = Attack).

## Module 2: BERT Tokenization (`tokenizer.py`)
* **Input:** Cleaned text data from Module 1.
* **Task:** Pass the text through HuggingFace's `bert-base-uncased` tokenizer. 
* **Output:** Input IDs and Attention Masks (tensors) ready for the neural network.

## Module 3: Model Definition (`model.py`)
* **Task:** Build the PyTorch class.
* **Layer 1 (Frozen):** The pre-trained BERT base model to generate embeddings.
* **Layer 2 (Trainable):** The DNN classifier (Dense layers, ReLU activation, Dropout, and final Sigmoid/Softmax output).

## Module 4: The Training Loop (`train.py`)
* **Task:** Feed the tokenized data into the model in batches.
* **Specs:** Use Adam optimizer, Cross-Entropy Loss (or BCELoss), and track the learning rate as defined in the paper's experimental setup.

## Module 5: Evaluation & Visualization (`evaluate.py` / Notebooks)
* **Task:** Test the model on unseen data.
* **Output:** Print the Classification Report (Accuracy, Precision, Recall, F1) and plot the Confusion Matrix.