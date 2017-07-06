# DeepLearning-Chatbot

A simple, experimental chatbot implementation.

Current functionalities include:

    Intent Classification [Using a Bidirectional LSTM based RNN]
    Entity Recognition [Using the Spacy NLP library for Python]
    Dependency Tree Display [Using the Spacy NLP Library for Python]
    Response Generation [Random text response generation using Stacked LSTM based RNN]
    
## Requirements:

   You will need a working installation of Python 3.5. (Preferrably on Anaconda - Installation Guide)
   The other requirements can be found here.

## Usage:

Provide your training datasets in the data/ folder.

Format: 

1. For intent classification:
    Each text file contains one sentence per line that is relevant to one particular class of intent. The textfile must be named after the intent that its sentences represent. The names of these text files will then be considered as the classes of intents, later used for training and prediction. The classification model uses a single bidirectional LSTM cell, followed by a dropout layer, with an Adam optimizer.
    The current dataset currently provided in data/intent_classification/ is small, but more data can be added or new training datasets can be used. The preprocessor.py file can be adjusted accordingly to read training input.

2. For text generation:
    Provide as much dialogue data as possible in a text file, as a sample for the type of text you want to generate.
    The current files provided include a variety of training data, each of which will result in a wildly different model, with respect to the style of responses generated.
    Much larger training relevant corpuses are required in order to train a robust, domain-specific chatbot. The current implementation of the response generation phase is a very basic word sequence generator, that uses 2 stacked LSTM cells, each followed by a dropout layer.
    Further commits will incorporate the response selector pipeline, that will ensure that the responses are more relevant to the user's query.
    
### To train the intent classification model on the training data:

python intent_train.py

### To test the intent classification model:

python intent_predict.py

### To train the response generation model:

python response_generation_train.py

### To generate a random response from the trained model:

python response_random_generate.py
    
