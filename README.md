# Number Classification API

This is a FastAPI application that classifies a given number based on various properties such as whether it is prime, perfect, Armstrong, odd or even. It also provides a fun fact about the number using the Numbers API.

## Features

- Check if a number is prime
- Check if a number is perfect
- Check if a number is an Armstrong number
- Determine if a number is odd or even
- Calculate the digit sum of a number
- Fetch a fun fact about the number

## Endpoints

### GET `/api/classify-number`

Classifies a given number and returns its properties.

#### Request Parameters

- `number` (query parameter): The number to classify. It should be a string representing a positive integer.

#### Response

- `number` (int): The input number.
- `is_prime` (bool): Whether the number is prime.
- `is_perfect` (bool): Whether the number is perfect.
- `properties` (list): List of properties (e.g., "armstrong", "odd", "even").
- `digit_sum` (int): The sum of the digits of the number.
- `fun_fact` (str): A fun fact about the number.

#### Example Request

```
GET /api/classify-number?number=153
```

#### Example Response

```json
{
    "number": 153,
    "is_prime": false,
    "is_perfect": false,
    "properties": ["armstrong", "odd"],
    "digit_sum": 9,
    "fun_fact": "153 is a triangular number."
}
```

## Installation

1. Clone the repository:
     ```sh
     git clone https://github.com/Heisobims/HNGINTERNSHIP-STAGE-01.git
     cd HNGINTERNSHIP-STAGE-01
     ```

2. Create a virtual environment and activate it:
     ```sh
     python -m venv venv
     source venv/bin/activate  # On Windows use `venv\Scripts\activate`
     ```

3. Install the dependencies:
     ```sh
     pip install -r requirements.txt
     ```

## Running the Application

1. Start the FastAPI server:
     ```sh
     uvicorn NumClass:app --reload
     ```

2. Open your browser and navigate to `http://127.0.0.1:8000/docs` to access the interactive API documentation.

## Dependencies

- FastAPI
- Uvicorn
- Requests

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## Contact

For any questions or suggestions, please contact [heisobims@gmail.com](mailto:heisobims@gmail.com).

## Additional Information

### Resources

- Fun fact API: [Numbers API](http://numbersapi.com/#42)
- [Parity (mathematics) - Wikipedia](https://en.wikipedia.org/wiki/Parity_(mathematics))

### Task Description

Create an API that takes a number and returns interesting mathematical properties about it, along with a fun fact.

### Requirements

- **Technology Stack**:
  - Use any programming language or framework of your choice (C#, PHP, Python, Go, Java, JS/TS)
  - Must be deployed to a publicly accessible endpoint
  - Must handle CORS (Cross-Origin Resource Sharing)
  - Must return responses in JSON format
- **Version Control**:
  - Code must be hosted on GitHub
  - Repository must be public
  - Must include a well-structured README.md

### API Specification

- **Endpoint**: `GET <your-domain.com>/api/classify-number?number=371`
- **Required JSON Response Format (200 OK)**:
  ```json
  {
      "number": 371,
      "is_prime": false,
      "is_perfect": false,
      "properties": ["armstrong", "odd"],
      "digit_sum": 11,
      "fun_fact": "371 is an Armstrong number because 3^3 + 7^3 + 1^3 = 371"
  }
  ```
- **Required JSON Response Format (400 Bad Request)**:
  ```json
  {
      "number": "alphabet",
      "error": true
  }
  ```

### Acceptance Criteria

- **Functionality**:
  - Accepts GET requests with a number parameter.
  - Returns JSON in the specified format.
  - Accepts all valid integers as the only possible inputs.
  - Provides appropriate HTTP status codes.
