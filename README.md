
## 🚘 Ethical Decision-Making with Transformers

This project fine-tunes a DistilBERT model to classify ethical decisions in **autonomous vehicle moral dilemmas**, such as choosing between protecting a pedestrian vs. the vehicle's occupants. It's designed to model moral reasoning using real and synthetic survey data.

---

### 📌 Project Goals

* Fine-tune a transformer on moral judgment data
* Classify ethical responses into:

  * `🚶‍♂️ Pedestrian Priority`
  * `🚗 Occupant Priority`
  * `🤷‍♀️ Uncertain / Random`
* Evaluate performance with accuracy and F1-score
* Deploy a **Gradio-based interactive demo**

---

### 📁 Dataset

The dataset is a combination of:

* Ethical decision survey responses (Google Form CSV)
* Paraphrased and augmented variants to expand classes
* Total samples: **86**
* Labels:

  * `0` → Pedestrian
  * `1` → Occupant
  * `2` → Uncertain / Random

---

### 🧠 Model

* **Base Model**: [`distilbert-base-uncased`](https://huggingface.co/distilbert-base-uncased)
* **Fine-tuning Task**: Sequence classification (3-class)
* **Loss**: CrossEntropyLoss
* **Optimizer**: AdamW

---

### 🏗️ Training Pipeline

```python
1. Load and label data from CSV
2. Tokenize using Hugging Face tokenizer
3. Convert into PyTorch Dataset & Dataloader
4. Fine-tune DistilBERT for 10 epochs
5. Evaluate using classification report (F1, precision, recall)
```

#### ✅ Sample Training Output:

```
Epoch 10 — Loss: 0.2417
Accuracy: 64%
```

---

### 📊 Evaluation Results

| Label        | Precision | Recall | F1   | Support |
| ------------ | --------- | ------ | ---- | ------- |
| Pedestrian   | 0.48      | 1.00   | 0.65 | 29      |
| Occupant     | 1.00      | 0.42   | 0.59 | 26      |
| Uncertain    | 1.00      | 0.48   | 0.65 | 31      |
| **Accuracy** |           |        | 0.64 | 86      |

---


### 🚀 Future Improvements

* Increase dataset size to >500 samples
* Include explanation generation (why model chose the decision)
* Fine-tune larger models (e.g., BERT or RoBERTa)
* Deploy to Hugging Face Spaces

---


### ✍️ Author

**Sreeja Mondal**
Undergraduate | IIIT Kalyani
Passionate about AI + Ethics 🤖⚖️

