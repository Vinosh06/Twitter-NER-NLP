# Twitter-NER-NLP


### Problem Statement

Twitter is a microblogging and social networking service on which users post and interact with messages known as "tweets". Every second, on average, around 6,000 tweets are tweeted on Twitter, corresponding to over 350,000 tweets sent per minute, 500 million tweets per day.

Twitter wants to automatically tag and analyze tweets for better understanding of the trends and topics without being dependent on the hashtags that the users use. Many users do not use hashtags or sometimes use wrong or mis-spelled tags, so they want to completely remove this problem and create a system of recognizing important content of the tweets.

Named Entity Recognition (NER) is an important subtask of information extraction that seeks to locate and recognise named entities.

You need to train models that will be able to identify the various named entities


### Data Description

Dataset is annotated with 10 fine-grained NER categories: person, geo-location, company, facility, product,music artist, movie, sports team, tv show and other. Dataset was extracted from tweets and is structured in CoNLL format., in English language. Containing in Text file format.

The CoNLL format is a text file with one word per line with sentences separated by an empty line. The first word in a line should be the word and the last word should be the label.


Consider the two sentences below;

Harry Potter was a student living in london

Albus Dumbledore went to the Disney World

These two sentences can be prepared in a CoNLL formatted text file as follows.

* Harry B-PER
* Potter I-PER
* was O
* a O
* student O
* Living O
* in O
* London B-geo-loc
* Albus B-PER
* Dumbledore I-PER
* went O
* to O
* the O
* Disney B-facility
* World I-facility


### Evaluation Criteria:
1. Defining problem statement, importing the data and data structure analysis
   * 1.1 Loading and formatting the data
2. Getting the correct model and tokenizer
3. Data preprocessing and tokenization
   * 1.1 Preparing the data in the correct format
   * 1.2 Tokenizing the data correctly
4. Train the model
5. Try different hyperparameters
6. Make predictions
   * 6.1 Join the subtokens
   * 6.2 Prediction on your own sentences


### Questions

1. Defining the problem statements and where can this and modifications of this be used?
2. Explain the data format (conll bio format)
3. What other ner data annotation formats are available and how are they different
4. Why do we need tokenization of the data in our case
5. What other models can you use for this task
6. Did early stopping have any effect on the training and results.
7. How does the BERT model expect a pair of sentences to be processed?
8. Why choose Attention based models over Recurrent based ones?
9. Differentiate BERT and simple transformers


### Process
* Import the test, train data and understand the structure of the data.
  - usual exploratory analysis steps like checking the structure & characteristics of the dataset
* Data preprocessing
  - Preparing the data in the format required by models
* Training a LSTM + CRF Model
  - Note: Please only use Tensorflow version 2.15 , run the below command
    * !pip install tensorflow==2.15
  - Use a word2vec model to initialize embeddings
* Train a Tensorflow Tokenizer
* Train test split the data
* Train the model
  - Understand the implications of using bidirectional models
  - Try various hyperparameters to improve results
* Align labels to input
  - Compute metrics to show effectiveness of trained model
* Loading the Transformer model
  - You can use the 'bert-base-uncased' model from the transformers library
  - Load the model and the model config
* Get the tokenizer for that model
* Tokenize the data
  - Understand what change tokenization has done to the data
  - After tokenizing check if the data is correct and do we need to remove or add some tokens
* Train test split the data
* Train the model on the data
  - Try various hyperparameters
  - Try different training epochs, early stopping, various optimizer,metrics
* Align the output for each sub tokens
  - Because we have result for sub tokens we need to combine back the tokens
* Make some predictions and see if the trained models are working fine
  - Save the transformers model with model.save_pretrained method
  - Check the result on some of your own sentences
