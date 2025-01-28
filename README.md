# Mental-Health-Chatbot

This project implements a simple chatbot using PyTorch. It includes scripts for training the chatbot model and interacting with users. The chatbot recognizes predefined intents and responds appropriately based on a trained neural network model.

## Files Overview

### `train.py`
This script is responsible for training the chatbot's neural network model. Key features include:

- **Data Loading**: Reads patterns and responses from `intents.json` and prepares training data.
- **Text Preprocessing**: Tokenizes, stems, and creates a bag-of-words representation of the input patterns.
- **Neural Network Training**: Trains a feed-forward neural network on the preprocessed data using PyTorch.
- **Hyperparameters**:
  - Number of epochs: `1000`
  - Batch size: `8`
  - Learning rate: `0.001`
  - Hidden layer size: `8`
- **Model Saving**: After training, the model's state dictionary and associated metadata are saved to `data.pth`.

### `chat.py`
This script implements the interactive chatbot. Key functionalities include:

- **Model Loading**: Loads the trained model from `data.pth`.
- **User Input Handling**: Tokenizes and transforms user input into a bag-of-words vector.
- **Intent Prediction**: Uses the trained neural network to predict the user's intent with softmax probabilities.
- **Response Selection**: Matches the predicted intent with a list of predefined responses in `intents.json`. If confidence is below 75%, the bot responds with a default message.
- **Chatbot Name**: The bot's name is set as `Hope`.

### `data.pth`
This file contains the trained model's parameters and metadata, including:

- Input size
- Hidden layer size
- Output size
- Model state dictionary
- Vocabulary (all_words)
- List of tags

## Prerequisites

- Python 3.7+
- PyTorch
- NLTK (for text preprocessing)
- JSON library

## Setup and Usage

1. **Training the Model**:
   - Ensure `intents.json` exists with defined intents, patterns, and responses.
   - Run `train.py` to train the model and save `data.pth`.

2. **Running the Chatbot**:
   - Ensure `data.pth` is available.
   - Run `chat.py` and interact with the chatbot.

## Customization

- **Survey to Enhance Intents**: Conducted a survey to gather more diverse patterns and responses, enriching the `intents.json` content.
- **Adding New Intents**:
  Update `intents.json` with new tags, patterns, and responses. Re-run `train.py` to incorporate changes.
- **Adjusting Hyperparameters**:
  Modify parameters like `num_epochs`, `batch_size`, or `hidden_size` in `train.py` for experimentation.

## Future Enhancements

- Adding natural language understanding for more flexible responses.
- Expanding the vocabulary and training data.
- Integrating external APIs for dynamic and context-aware responses.
