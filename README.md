# mlops_hw_1

# Machine Learning Model Training API

This API allows users to train, predict, and manage machine learning models using FastAPI and scikit-learn.

## Getting Started

### Installation

1. Clone this repository.

    ```bash
    git clone https://github.com/weegaboo/mlops_hw_1.git
    cd mlops_hw_1
    ```

2. Install dependencies.

    ```bash
    pip install -r requirements.txt
    ```

### Running the API

Run the API using the following command:

```bash
python app.py
```

The API will start running at http://localhost:64094.

## API Endpoints

### Train a Model

- **Endpoint**: `/train`
- **Method**: `POST`
- **Description**: Train a machine learning model based on provided data.
- **Request Body**:
    ```json
    {
        "features": [...],
        "labels": [...],
        "model_type": "RandomForest",
        "hyperparameters": {
            "n_estimators": 100,
            "max_depth": 5
            // Other hyperparameters based on the model
        }
    }
    ```
- **Response**:
    ```json
    {
        "message": "Model trained successfully",
        "model_id": 1
    }
    ```

### Get Available Models

- **Endpoint**: `/models`
- **Method**: `GET`
- **Description**: Retrieve available model IDs.
- **Response**:
    ```json
    {
        "models": [1, 2, 3]
    }
    ```

### Predict Using a Model

- **Endpoint**: `/predict`
- **Method**: `POST`
- **Description**: Make predictions using a trained model.
- **Request Body**:
    ```json
    {
        "model_id": 1,
        "features": [[...]]
    }
    ```
- **Response**:
    ```json
    {
        "prediction": 1
    }
    ```

### Delete a Model

- **Endpoint**: `/delete/{model_type}`
- **Method**: `DELETE`
- **Description**: Delete a trained model.
- **Response**:
    ```json
    {
        "message": "Model deleted successfully"
    }
    ```

## Contributing

Contributions are welcome! Fork the repository and submit a pull request.

