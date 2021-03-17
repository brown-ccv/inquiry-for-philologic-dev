# inquiry-for-philologic-analysis

This code is an NLP pipeline for topic modeling large collections of documents. It is generalizeable to any text data set, once formatted properly (see `src-gen/raw_corpus2tsv.py` for an example processing script). 

This code is run on a compute cluster at Brown University using the slurm scheduler. Minor adjustments should allow the code to be run on other compute clusters or locally.

## Requirements
* Python 3.6.1
* MALLET
* numpy
* pandas
* sys
* os
* time
* string
* csv
* pickle
* sklearn
* nltk
* enchant

## Running the Code on Any Data Set
The folder for running the code on any data set is in `src-gen/`. 
* `main.py`: The top level script which contains the pipeline steps. There are two steps (converting your data to the tab-separated file and doing custom data cleaning) that are specific to your data and should be written as such. Subsequent steps will run without modification so long as your data file is formatted correctly. 
* `preprocess.py`: The script for doing a variety of natural language processing tasks to clean and prepare the data for topic modeling.
* `mallet.py`: Python wrappers for the following two shell scripts.
* `mallet_import_from_file.sh`: The script to import the data into MALLET.
* `mallet_train_lda.sh`: The script to create a Latent Dirichlet Model (LDA) of the corpus.
* `rank_documents.py`: Create document rankings based on document-topic matrix normalized row sums.
