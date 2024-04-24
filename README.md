# NER-with-Bi-LSTM
Named Entity Recognition using Bi-directional LSTM

**Repository Title: Named Entity Recognition with Word Embeddings**

**Description:**
This repository contains Python code for Named Entity Recognition (NER) using word embeddings, implemented with the help of deep learning techniques and natural language processing libraries. The NER system identifies and classifies named entities in text data into predefined categories such as persons, organizations, locations, and miscellaneous entities.

**Installation:**
1. Clone the repository:
   ```
   git clone https://github.com/yourusername/ner-word-embeddings.git
   ```

2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

**Usage:**
1. Data Preprocessing:
   - Use `preprocess.file_preprocessing(file_name)` to preprocess raw data.
   - Use `preprocess.create_OHE(data, col, labels_)` to perform one-hot encoding on the NER labels.
   - Use `preprocess.word2vec_token(model, data, WORD_DIMENSIONS)` to tokenize words into word embeddings.

2. NER Prediction:
   - Use the trained model to predict NER tags on new text data.
   - Use `decode_tag(tag)` to decode one-hot encoded NER tags into human-readable labels.

**Example Usage:**
```python
from preprocess import preprocess
from model import model
from decode_tag import decode_tag

# Initialize preprocessing class
pre = preprocess()

# Preprocess data and save as pickle files
pre.save_pkl("data.csv", "input_data.pkl", "output_data.pkl")

# Train the model
model.train("input_data.pkl", "output_data.pkl")

# Predict NER tags on new text
sentence = "John works at Google in California"
tags = model.predict_ner(sentence)

# Decode NER tags
decoded_tags = [decode_tag(tag) for tag in tags]
print(decoded_tags)
```

**Contributing:**
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/new-feature`).
3. Make your changes and commit (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature/new-feature`).
5. Create a new pull request.
