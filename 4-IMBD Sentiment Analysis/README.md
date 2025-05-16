# 🎬 IMDB Movie Review Sentiment Analysis - Deep Learning Project

## Table of Contents
- [🌟 Overview](#-overview)
- [🛠️ Technologies Used](#-technologies-used)
- [📊 Dataset Description](#-dataset-description)
- [🚀 Methodology](#-methodology)
- [🧠 Model Architecture](#-model-architecture)
- [📈 Results](#-results)
- [🎉 Demo](#-demo)
- [🔮 Future Work](#-future-work)
- [🛠️ How to Use](#-how-to-use)

---

## 🌟 Overview
This project builds a **deep learning model** to classify IMDB movie reviews as `positive` or `negative` using NLP and LSTM networks. Key features:
- Text preprocessing with **spaCy** (lemmatization, stopword removal)
- **Bidirectional LSTM** with regularization for robust learning
- **Gradio** web app for real-time sentiment prediction
- Achieves **~85-90% accuracy** on test data

---

## 🛠️ Technologies Used

### Core Libraries
- **Python**  
  ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
- **TensorFlow/Keras**  
  ![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
- **spaCy** (NLP preprocessing)  
  ![spaCy](https://img.shields.io/badge/spaCy-09A3D5?style=for-the-badge&logo=spacy&logoColor=white)
- **Gradio** (Web UI)  
  ![Gradio](https://img.shields.io/badge/Gradio-FF4B4B?style=for-the-badge&logo=gradio&logoColor=white)

### Supporting Libraries
- Pandas | NumPy | Matplotlib | Scikit-learn

---

## 📊 Dataset Description
**Processed_IMDB_Dataset3.csv** contains:
- **review**: Raw text of movie reviews
- **sentiment**: Labels (`positive` or `negative`)
- **cleaned_review**: Processed text after:
  - URL/email removal
  - Special character filtering
  - Lemmatization & stopword removal

**Class Distribution**: Balanced (~50% positive, 50% negative)

---

## 🚀 Methodology

### 1. **Text Preprocessing**
```python
def clean_text(text):
    # Remove URLs, emails, special chars
    text = re.sub(r'http\S+|\S+@\S+|[^a-zA-Z\s]', '', text)
    
    # spaCy pipeline: lemmatization + stopword removal
    doc = nlp(text)
    return ' '.join([token.lemma_.lower() for token in doc 
                    if not (token.is_punct | token.is_stop | token.is_space)])
```

### 2. **Feature Engineering**
- **Tokenization**: Top 1000 frequent words
- **Padding**: Fixed-length sequences (`max_len=100`)
- **Train-Test Split**: 75%-25%

### 3. **Model Training**
- Early stopping with `patience=3`
- Validation split (20% of training data)

---

## 🧠 Model Architecture
```python
model = Sequential([
    Embedding(1000, 64, input_length=100),
    SpatialDropout1D(0.3),
    Bidirectional(LSTM(64, dropout=0.3, recurrent_dropout=0.3)),
    Dense(64, activation='relu', kernel_regularizer=l2(0.01)),
    Dropout(0.5),
    Dense(1, activation='sigmoid')
])
```
**Key Techniques**:
- **Bidirectional LSTM**: Captures contextual relationships
- **Regularization**: Dropout + L2 to prevent overfitting
- **Optimizer**: Adam with binary cross-entropy loss

---

## 📈 Results
- **Test Accuracy**: 85-90% 
- **Sample Predictions**:
  - "Beautiful cinematography" → `positive`
  - "The film is boring" → `negative`
- **Training Curve**:  
  ![Training History](https://via.placeholder.com/400x200/3776AB/FFFFFF?text=Accuracy+and+Loss+Curves)

---

## 🎉 Demo
**Gradio Web App**:  
![Gradio Interface](https://via.placeholder.com/600x300/FF4B4B/FFFFFF?text=Gradio+Web+App)

Run locally:
```bash
python app.py
```
Access via public URL when launched with `share=True`.

---

## 🔮 Future Work
- **Deployment**: Dockerize app for cloud deployment
- **Advanced Models**: Experiment with Transformers (BERT)
- **Multi-class Classification**: Add neutral sentiment

---

## 🛠️ How to Use

### 1. **Installation**
```bash
pip install -r requirements.txt  # Includes tensorflow, spacy, gradio
python -m spacy download en_core_web_sm
```

### 2. **Run Training**
```bash
python train.py
```

### 3. **Launch Web App**
```bash
python app.py
```

### 4. **Make Predictions**
```python
from utils import load_model
model, tokenizer = load_model()
model.predict_sentiment("This movie exceeded my expectations!")
# Output: 'positive'
```

### Saved Models
- `imdb_model.h5`: Trained Keras model
- `tokenizer.pkl`: Fitted tokenizer

---

Let me know if you'd like to add deployment instructions or expand any section!
