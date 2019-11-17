In the notebook shared there are 2 models implemented by me:
The pre-processing is the same that has been carried out for both the models. ALll the user tags, IDs, hashtags, alpha-numerical terms are removed and only 
pure hindi and English terms are kept for further processing.
Model 1:
The cleaned tweets are converted into embeddings using the BERT architecture. This is then used for the classification task.
Each tweet was hence converted into a vector of size 1*768. These 768 features are used for classification. 
The core model consists of the following layers
Layer 1: An embedding layer of a vector size of 768.
Layer 2: 128 cell bi-directional LSTM layers, where the embedding data is fed to the network. I added a dropout of 0.2 this is used to prevent overfitting.
Layer 3: A 512 layer dense network which takes in the input from the LSTM layer. A Dropout of 0.5 is added here.
Layer 4: A 10 layer dense network with softmax activation, each class is used to represent a sentiment category, with class 1 representing sentiment score between 0.0 to 0.1 and class 10 representing a sentiment score between 0.9 to 1.

Model 2:
The only difference is the embeddings are used from the flair library and are of the size 35*3072. These are set after padding all embeddings equally.
These are
