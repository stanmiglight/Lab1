# Factorial Calculator API

This project is a simple RESTful API built with [FastAPI](https://fastapi.tiangolo.com/) that calculates the factorial of a given integer. The API takes an integer input and returns its factorial as a JSON response.

## Features
- Calculate the factorial of a positive integer.
- Handles edge case for `0!` (which is defined as `1`).
- Returns a `false` result for invalid input (e.g., `0`).

## Requirements

Before running the API, ensure you have the following installed:
- Python 3.7+
- FastAPI
- Uvicorn (for running the server)

## Installation

1. Clone this repository or copy the `main.py` file.
2. Install the required Python packages:
   ```bash
   pip install fastapi uvicorn
   ```

## Running the API

To run the API locally, execute the following command in your terminal:
```bash
uvicorn main:app --reload
```

- The server will start at `http://127.0.0.1:8000`.

## Endpoints

### Calculate Factorial

**GET** `/factorial/{starting_number}`

#### Parameters:
- `starting_number` (int): The number whose factorial is to be calculated. Must be a positive integer.

#### Response:
- If `starting_number` is valid:
  ```json
  {
      "result": <factorial_of_starting_number>
  }
  ```
- If `starting_number` is `0` or invalid:
  ```json
  {
      "result": false
  }
  ```

#### Example Usage:
1. Request:
   ```
   GET http://127.0.0.1:8000/factorial/5
   ```
   Response:
   ```json
   {
       "result": 120
   }
   ```

2. Request:
   ```
   GET http://127.0.0.1:8000/factorial/0
   ```
   Response:
   ```json
   {
       "result": false
   }
   ```

## Notes
- Factorials are calculated iteratively for simplicity.
- This project is intended for educational purposes or as a basic template for learning FastAPI.

## Contributions
Feel free to submit issues or pull requests if you have improvements or suggestions!
