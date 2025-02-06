# Urdu to English Machine Translation with RNN + Attention

## 📌 Project Overview
This project implements a **Recurrent Neural Network (RNN) with an Attention-based Encoder-Decoder model** for **Urdu-to-English machine translation**. The model is trained from scratch using the **PyTorch** framework and does **not** rely on pre-built architectures like RNN or LSTM libraries.

The **goal** is to translate Urdu sentences into English, leveraging an **attention mechanism** to improve translation quality. The performance is evaluated using the **BLEU score** via the Moses multi-bleu script.


---

## 📜 Dataset
The dataset consists of **parallel Urdu-English sentences** provided in `.dev` and `.devtest` files. The preprocessing steps include:
- **Combining both files** into a single dataset
- **Tokenization & cleaning** (removing punctuation, lowercasing, whitespace normalization)
- **Splitting** into **70% training, 15% validation, and 15% test**
- **Building vocabularies** with special tokens (`<pad>`, `<sos>`, `<eos>`, `<unk>`)

---

## 🔧 Model Architecture
The model follows an **Encoder-Decoder** approach:

### 🔹 Encoder
- Embedding layer for Urdu input
- **Custom LSTM cell (manually implemented)**
- Outputs a hidden state vector passed to the decoder

### 🔹 Attention Mechanism
- **Bahdanau-style attention** to improve context understanding
- Dynamically computes importance weights over encoder outputs

### 🔹 Decoder
- Embedding layer for English output
- **Custom LSTM cell (manually implemented)**
- Generates translated sequences **one word at a time**
- Uses the attention context vector for better performance

---

## 🔥 Training & Optimization
- **Loss Function:** CrossEntropyLoss (ignoring `<pad>` token)
- **Optimizer:** Adam with gradient clipping (max norm = 1.0)
- **Batch Size:** 16
- **Max Sequence Length:** 50
- **Epochs:** 50 (with early stopping if validation loss stabilizes)

---

## 📊 Evaluation Metrics
- **BLEU Score** (Moses multi-bleu script) to measure translation quality
- **Validation & Training Loss Tracking**
- **Prediction Accuracy** (token-level comparison)

---

## 📌 Results & Visualizations
- **Loss vs Epochs graph**
- **BLEU score vs Epochs graph**
- **Comparison table for training, validation, and test BLEU scores**


---

## ⚡ Future Improvements
- Implement **Transformer-based models** for better accuracy
- Train with **larger datasets** for improved generalization
- Experiment with **different attention mechanisms**

---

## 🛠 Tech Stack
- **Python, PyTorch, NumPy**
- **Moses BLEU Evaluation**
- **Matplotlib (for visualizations)**


