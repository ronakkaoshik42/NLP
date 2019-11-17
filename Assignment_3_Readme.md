In the notebook shared there are 2 models implemented by me:
The pre-processing is the same that has been carried out for both the models. ALll the user tags, IDs, hashtags, alpha-numerical terms are removed and only 
pure hindi and English terms are kept for further processing.
Model 1:
The cleaned tweets are converted into embeddings using the BERT architecture. This is then used for the classification task.
Each tweet was hence converted into a vector of size 1*768. These 768 features are used for classification. 
The core model consists of the following layers
Layer 1: An embedding layer of a vector size of 768.
Layer 2: 128 cell bi-directional LSTM layers, where the embedding data is fed to the network. I added a dropout of 0.2 this is used to prevent overfitting.
Layer 3: A 20 layer GRU layer which takes in the input from the LSTM layer. A Dropout of 0.2 is added here.
Layer 4: A 3 layer dense network at the output with softmax activation, each class is used to represent a sentiment category.

accuracy, f1_score, precision (Macro-Avg)
0.4820759766174549, 0.47512554012561875, 0.4885379824490392 

Model 2:
The only difference is the embeddings are used from the flair library and are of the size 31*3072. These are set as training and testing after padding all embeddings equally.

accuracy, f1_score, precision (Macro-Avg)
0.5163188872967511, 0.5129973308296367, 0.5214308757970778
