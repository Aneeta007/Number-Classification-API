
📌 Number Classification API

📖 Overview

The Number Classification API is a serverless API deployed on AWS Lambda and API Gateway. It accepts a number as input and returns its mathematical properties along with a fun fact from the Numbers API.

✨ Features

🟢 Checks if a number is Prime, Perfect, or Armstrong

🔢 Identifies whether a number is odd or even

🔍 Calculates the sum of digits of the number

🎉 Fetches a fun fact about the number using Numbers API

🌍 CORS-enabled for cross-origin requests

⚡ Fast response time (<500ms)

🚀 Serverless architecture using AWS Lambda & API Gateway

📂 Version-controlled on GitHub with structured documentation

🛠️ Tech Stack

AWS Lambda (Backend Execution)

API Gateway (Public API Hosting)

Python 3.x (Programming Language)

Numbers API (External Fun Fact API)

GitHub (Version Control)

📌 API Specification

🔹 Endpoint

GET <your-api-url>/api/classify-number?number=<value>

🔹 Example Request

curl -X GET "<your-api-url>/api/classify-number?number=371"

🔹 Successful Response (200 OK)

{
    "number": 371,
    "is_prime": false,
    "is_perfect": false,
    "properties": ["armstrong", "odd"],
    "digit_sum": 11,
    "fun_fact": "371 is an Armstrong number because 3^3 + 7^3 + 1^3 = 371"
}

🔹 Error Response (400 Bad Request)

{
    "number": "invalid_input",
    "error": true
}

🏗️ How It Works

User sends a GET request with a number as a query parameter.

API validates the number, ensuring it's a valid integer or float.

Calculates properties (prime, perfect, Armstrong, odd/even, digit sum).

Fetches a fun fact from the Numbers API.

Returns a structured JSON response.

🚀 Deployment on AWS Lambda

Step 1: Create an AWS Lambda Function

Go to AWS Lambda and click Create function.

Choose Author from scratch.

Runtime: Python 3.x.

Upload the lambda_function.py file.

Set the Handler to lambda_function.lambda_handler.

Increase Timeout to 5 seconds.

Step 2: Configure API Gateway

Go to API Gateway and create a REST API.

Add a new GET method linked to your Lambda function.

Enable CORS (Cross-Origin Resource Sharing).

Deploy the API and copy the public endpoint URL.

Step 3: Test API

Run:

curl -X GET "<your-api-url>/api/classify-number?number=371"

You should receive a JSON response with number properties and a fun fact.

🛠️ Local Development & Testing

1️⃣ Clone the Repository

git clone <your-github-repo-url>
cd number-classification-api

2️⃣ Install Dependencies

pip install requests

3️⃣ Run Locally

python lambda_function.py

4️⃣ Test Locally

import lambda_function

test_event = { "queryStringParameters": {"number": "371"} }
print(lambda_function.lambda_handler(test_event, None))

🎯 Challenges Faced & Fixes

✅ 500 Internal Server Error for Negative Numbers → Now returns 200 OK for all valid numbers (negative & floating-point supported).
✅ Syntax Errors in Lambda Function → Fixed improper JSON formatting in response handling.
✅ CORS Issues → Implemented correct CORS headers in the response.
✅ Slow Response Time → Optimized API request handling and logic execution.
