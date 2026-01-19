# Next Word Prediction with LSTM (Hamlet) + Streamlit App

This project builds a Next Word Prediction model using an LSTM language model trained on Hamlet text. Given a partial phrase, the model predicts the most likely next word and can be used interactively through a Streamlit web app.

What This Project Does

Loads and tokenizes text line-by-line

Creates training sequences using n-grams (prefix → next word)

Pads sequences to a uniform length for model training

Trains an LSTM-based neural network to learn word-to-word patterns

Provides an interactive Streamlit UI to test next-word predictions in real time

How Training Data Is Generated (N-gram Sequences)

For each line of text, the pipeline generates incremental sequences.
Example: "to be or not to be" becomes:

to → be

to be → or

to be or → not

to be or not → to

to be or not to → be

This is done programmatically by building input_sequences from each tokenized line, where:

X = all words except the last

y = the last word (the “next word” label)

Model Training Notes

The model was trained for 200 epochs on my local machine.

Training took 72 minutes for 200 epochs.

Accuracy can likely be improved further with:

More epochs (e.g., 500+)

Larger model capacity

Better regularization / tuning (dropout, learning rate scheduling)

More training data

Streamlit App

A Streamlit app is included to:

Enter a prompt (partial sentence)

Get the next predicted word

Quickly test how well the model completes phrases learned from the dataset
