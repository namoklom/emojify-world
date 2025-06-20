# Emojify World! (Text to Emoji Prediction with GloVe and LSTM)

## 👤 Author

| Name            | Role              | LinkedIn                                      |
|-----------------|-------------------|-----------------------------------------------|
| Jason Emmanuel  | AI Engineer    | [linkedin.com/in/jasoneml](https://www.linkedin.com/in/jasoneml/) |

Welcome to **Emojify World!** This project explores the exciting intersection of Natural Language Processing (NLP) and Deep Learning by building a system that can understand short text messages and suggest the most fitting emoji in response. It's like giving your messages a personality boost through AI-powered emotion detection.

In today's digital communication, emojis play a vital role in expressing emotions and tone. However, choosing the right emoji isn't always straightforward. This project addresses that by creating a model that automatically maps sentences to emojis, helping users communicate more vividly and intuitively.

The system is trained on a dataset of short sentences labeled with emojis, using word embeddings from GloVe to capture semantic meaning. It includes two models: a baseline model that averages word vectors (Emojifier-V1), and a more advanced LSTM-based model (Emojifier-V2) that learns the sequential structure of language.

Whether you're a beginner in NLP or looking to deepen your understanding of sequence modeling with real-world applications, **Emojify World** is a fun and educational project that shows how machine learning can add expressive intelligence to everyday interactions. 🤖💬➡️😊

---

## 🌟 Project Highlights

- 📖 Converts short sentences into emoji expressions.
- 🧠 Built with both classical NLP techniques and modern LSTM networks.
- 🧰 Uses **GloVe word vectors** for pretrained semantic understanding.
- ✅ Includes **baseline model**, **advanced LSTM model**, and **unit tests**.
- 📊 Shows confusion matrix, predictions, and accuracy.

---

## 📊 Dataset Details

The dataset contains short English sentences mapped to one of 5 emoji labels:

| Label | Emoji | Meaning         |
|-------|:-----:|-----------------|
| 0     | ❤️    | Love            |
| 1     | ⚾    | Play/Sports     |
| 2     | 😄    | Smile/Happiness |
| 3     | 😞    | Sadness         |
| 4     | 🍴    | Food            |

- **train_emoji.csv**: 132 examples
- **tesss.csv**: 56 examples

---

## 🧠 Model Architectures

### 🔹 Emojifier-V1: Averaged Word Embeddings + Softmax

A simple baseline model that averages word embeddings from GloVe for each sentence and passes the result through a softmax classifier.

**Architecture:**

<img width="858" alt="emojifierv1" src="https://github.com/user-attachments/assets/68d19831-770c-4467-9464-8ab2cf654a83" />

- **Embedding Source**: GloVe 6B (50-dimensional)
- **Trainable Parameters**: No (embeddings are fixed)
- **Optimizer**: Adam
- **Loss Function**: Categorical Crossentropy

### 🔹 Emojifier-V2: LSTM-based Deep Learning Model

A more sophisticated model using an LSTM to capture word order and context in the sentence.

**Architecture:**

<img width="833" alt="emojifier-v2" src="https://github.com/user-attachments/assets/0965d401-f6f1-4c58-b1b2-69562e05683c" />

- **Embedding Source**: GloVe 6B (50-dimensional, non-trainable)
- **Sequence Length**: 10 tokens (max)
- **Trainable Parameters**: Yes (LSTM & Dense layers)
- **Optimizer**: Adam
- **Loss Function**: Categorical Crossentropy

---

## 📈 Model Performance

| Model            | Train Accuracy | Test Accuracy |
|------------------|----------------|----------------|
| Emojifier-V1     | 97.7%          | 85.7%          |
| Emojifier-V2     | 99.2%          | 87.5%          |

- **V1** performs well using basic embeddings, but lacks sequential understanding.
- **V2** captures word order/context with LSTM, yielding slightly better test performance.
- Both models are evaluated using top-1 accuracy

---

## 🛠️ Tools and Libraries Used

| Tool / Library       | Purpose                                                                 |
|----------------------|-------------------------------------------------------------------------|
| Python               | Primary programming language                                            |
| NumPy                | Numerical operations and matrix manipulation                            |
| Pandas               | CSV data handling and data preprocessing                                |
| Matplotlib           | Plotting and visualizing model metrics                                  |
| GloVe (glove.6B.50d) | Pre-trained word embeddings for semantic understanding of text          |
| TensorFlow / Keras   | Building and training deep learning models (LSTM for Emojifier-V2)      |
| emoji (Python pkg)   | Displaying and mapping text labels to emojis                            |
| Jupyter Notebook     | Interactive environment for development, testing, and visualization     |

---

## 🔧 Setup Instructions

### Clone the Repository

```bash
git clone https://github.com/namoklom/emojify-world.git
cd emojify-world
```
