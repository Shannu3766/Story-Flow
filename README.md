# Story Flow

**Story Flow** is a deep learning-based sentence completer, trained on text data from stories. It uses tokenization and sequence prediction to generate a continuation of a sentence based on an input seed text.

## Prerequisites

- Python 3.12+
- SpaCy (with `en_core_web_sm` model)
- TensorFlow/Keras
- Numpy

## Project Structure

1. **Loading the SpaCy Model**  
   The small English model (`en_core_web_sm`) from SpaCy is loaded with some components disabled (`parser`, `tagger`, `ner`) to focus on tokenization.

2. **Data Loading**  
   The function `read_book()` reads a text file (such as *Moby Dick*), and `separate_punctuation()` tokenizes the text while removing unwanted punctuation.

3. **Text Preprocessing**  
   Tokenized sequences are generated from the text, with each sequence consisting of 25 words for training the model.

4. **Model Training**  
   A neural network built with TensorFlow/Keras is trained on these sequences to predict the next word in a sentence.

5. **Sentence Generation**  
   The `generate_text()` function takes an input seed text and generates a sequence of words based on the trained model.

## Usage

To use **Story Flow**:

1. Clone the repository and install the required dependencies:
   ```bash
   pip install spacy tensorflow numpy
   python -m spacy download en_core_web_sm
