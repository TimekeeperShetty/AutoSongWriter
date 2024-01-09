# AutoSongWriter

An automatic lyrics generator is used to produce new song lyrics based on patterns learned from existing lyrics. While these are not intended to replace human creativity, they provide a powerful resource for enhancing the songwriting process and make it easier for beginner songwriters. This project applies recurrent neural networks (RNNs) with Long Short-Term Memory (LSTM) layers, to understand the structure, style, and language of song lyrics. The model learns to generate coherent and contextually relevant lyrics that resemble the input data it was trained on.

Libraries Used:

Numpy: A powerful library for numerical operations and handling multi-dimensional arrays. It is widely used in scientific computing and machine learning.

Pandas: A data manipulation library for handling structured data. It provides data structures like DataFrames for efficient data analysis and manipulation.

TensorFlow and Keras: TensorFlow, along with the high-level Keras API, empowers the creation and training of a neural network for automatic lyrics generation.

Scikit-learn: scikit-learn aids in splitting the dataset into training and testing sets, a fundamental step in machine learning model development.

Process Steps

1. Data Loading:
The project begins by loading MIDI files containing musical data and a dataset of song lyrics. The lyrics dataset is cleaned to remove irrelevant entries.

2. Text Preprocessing:
Text preprocessing involves converting song lyrics into a suitable format for model training. It includes removing unwanted characters, converting text to lowercase, and organizing the data into structured sections (e.g., verses and choruses).

3. Dataset Creation:
The project creates a unified dataset by combining lyrics from songs and additional poetry data. The text is split into smaller sequences, and sequences containing uncommon words are filtered out. This prepares the data for training a language model.

4. Tokenization and Word Indexing:
Text is tokenized into individual words, and each unique word is assigned a numerical index. This process is crucial for representing the text in a format that the machine learning model can understand.

5. Model Construction:
A neural network model is constructed using Keras. It includes an embedding layer, a bidirectional LSTM layer, and a dense layer with softmax activation for word prediction.

6. Model Training:
The model is trained on the prepared dataset. A generator function is used to feed batches of data to the model during training. 

7. Epoch-wise Text Generation:
After each training epoch, the model generates new text sequences based on a randomly selected seed. The diversity of generated sequences is controlled by a temperature parameter. Generated text samples are saved for evaluation.

8. Model Evaluation and Saving:
The model's performance is monitored during training, and checkpoints are saved. Additionally, an early stopping mechanism is implemented to prevent overfitting. The best-performing model is saved for future use.

Possible Improvements:

1) Model Fine-Tuning: Experiment with different neural network architectures and hyperparameter settings to optimize the model's lyric generation capabilities.
2) Embedding Layer Optimization: Explore pre-training the embedding layer on extensive text data to capture nuanced word representations, resulting in richer and more contextually aware lyrics.
3) Dynamic Sequence Handling: Allow for variable sequence lengths during training to better capture different song structures, accommodating varying verse and chorus lengths.
