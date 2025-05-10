# 🧠 English to Italian Translation using Seq2Seq + Attention

This project implements a neural machine translation (NMT) model using an encoder-decoder architecture with attention mechanisms. It translates English sentences to Italian using a dataset of bilingual sentence pairs.

---

## 📌 Project Highlights

- Implements a Seq2Seq model with LSTM-based encoder and decoder
- Explores three attention scoring methods: **dot**, **general**, and **concatenation**
- Uses GloVe embeddings for the English vocabulary
- Evaluates performance using **BLEU scores** and **attention visualizations**

---

## 📂 Dataset

- Source: [ManyThings.org](http://www.manythings.org/anki/)
- Language Pair: English ↔ Italian
- Format: Tab-separated sentence pairs
- Preprocessing:
  - Sentence length capped at 20 tokens
  - Special tokens `<start>` and `<end>` added for decoder training

---

## 🧱 Model Architecture

- **Encoder**:
  - Embedding layer (50d)
  - LSTM layer with 256 units
- **Decoder**:
  - Embedding layer (100d)
  - LSTM layer with 256 units
  - Attention mechanism (dot, general, concat scoring)
- **Output**:
  - Dense layer with softmax activation over vocabulary

---

## 📈 Evaluation & Results

| Model Variant                               | BLEU Score |
|---------------------------------------------|------------|
| Encoder-Decoder (no attention)              | 60.8       |
| Encoder-Decoder + Attention (dot scoring)   | 65.8       |
| Encoder-Decoder + Attention (general scoring)| 66.6       |
| Encoder-Decoder + Attention (concat scoring)| 66.8       |

- **Attention** mechanisms improved translation quality over baseline
- **Concat scoring** gave the best BLEU score and alignment maps

---

## 🔍 Sample Output

```plaintext
Input: I love you
Predicted: Ti amo

Input: How are you?
Predicted: Come stai?

(More examples and attention maps can be found in the notebook.)
