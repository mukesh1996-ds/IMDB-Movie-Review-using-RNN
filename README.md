# IMDB Review Sentiment Analysis Using Simple RNN

This project aims to classify IMDB movie reviews as positive or negative using a Simple Recurrent Neural Network (RNN). The solution involves a comprehensive pipeline from dataset preparation to deployment as a web application using Streamlit.

## Project Workflow

1. **Dataset Preparation**  
   The IMDB dataset is used for training and evaluation. This dataset contains reviews labeled as positive or negative.

2. **Feature Engineering**  
   Text data is preprocessed, tokenized, and converted to sequences. The sequences are then padded to ensure uniform input dimensions.

3. **Simple RNN with Embedding Layer**  
   A Simple RNN model is implemented with an Embedding layer for word vector representation. This architecture is trained to classify sentiments.

4. **Model Export**  
   The trained model is saved in `.h5` format for integration and deployment.

5. **Streamlit Web Application**  
   A user-friendly web interface is built using Streamlit, allowing users to input reviews and get real-time predictions.

6. **Deployment**  
   The application is deployed to a cloud platform, making it accessible to end users.

---

## RNN Architecture

### Architecture Overview

The RNN consists of the following layers:  
1. **Embedding Layer**  
   Converts input words into dense vector representations of a fixed size.

2. **Simple RNN Layer**  
   Processes sequential data by maintaining a hidden state that captures temporal dependencies.

3. **Fully Connected (Dense) Layer**  
   A dense layer with a single neuron and sigmoid activation for binary classification (positive/negative sentiment).

---

### Detailed Architecture

- **Input Layer**  
  Accepts preprocessed text sequences of a fixed length.

- **Embedding Layer**  
  - Input: Word indices (integers) from the vocabulary.  
  - Output: Dense vector representations for each word.  
  - Example: Convert a sentence into a sequence of word vectors.

- **Simple RNN Layer**  
  - Input: Word vectors from the embedding layer.  
  - Output: A sequence of hidden states.  
  - Maintains temporal relationships between words using hidden state propagation.

- **Dense Output Layer**  
  - Activation: Sigmoid.  
  - Output: A probability score indicating positive or negative sentiment.

---

### Model Summary (Example)

```plaintext
Layer (type)               Output Shape            Param #
=================================================================
embedding (Embedding)      (None, 200, 128)        1280000
simple_rnn (SimpleRNN)     (None, 128)             32896
dense (Dense)              (None, 1)               129
=================================================================
Total params: 1,313,025
Trainable params: 1,313,025
Non-trainable params: 0
```

---

## How to Run the Project

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Train the Model**  
   Run the training script to train the model:
   ```bash
   python train_model.py
   ```

4. **Launch the Web Application**  
   Start the Streamlit app:
   ```bash
   streamlit run app.py
   ```

---

## Deployment

The Streamlit app can be deployed to cloud platforms such as **Heroku**, **AWS**, or **Streamlit Sharing**. Detailed instructions for deployment can be found in the `deployment.md` file.

---

## Future Enhancements

- Incorporate **Bidirectional RNN** or **LSTM** for improved performance.  
- Add a feature for user feedback collection on predictions.  
- Integrate multilingual sentiment analysis capabilities.
```
