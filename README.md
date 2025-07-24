# Emotion Classification Demo

This repository contains a simple emotion classification service using FastAPI and the Hugging Face Transformers library. The service uses a pre-trained ALBERT model fine-tuned for emotion detection.

## Features

- **FastAPI**: Provides a simple HTTP interface for emotion classification.
- **Transformers**: Utilizes the `bhadresh-savani/albert-base-v2-emotion` model from Hugging Face for text classification.
- **Asynchronous Lifespan**: The model is loaded asynchronously when the application starts.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/nikhilpopli4900/emotion-classification-demo.git
   cd emotion-classification-demo
   ```

2. Install the required packages:
   ```bash
   pip install fastapi transformers uvicorn
   ```

3. Run the FastAPI app:
   ```bash
   uvicorn app:app --reload
   ```

   The service will be available at `http://127.0.0.1:8000/`.

## Usage

- **Endpoint**: `/predict`
- **Method**: `POST`
- **Request Body**:
  ```json
  {
    "inputs": ["I am happy", "I am angry", "I am sad"],
    "parameters": {}
  }
  ```

- **Response**:
  ```json
  [
    {"label": "joy", "score": 0.99},
    {"label": "anger", "score": 0.98},
    {"label": "sadness", "score": 0.97}
  ]
  ```

## Example

To make a prediction, send a POST request to the `/predict` endpoint with the input text you want to classify.

## License

This project is licensed under the MIT License.
