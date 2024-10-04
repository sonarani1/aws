# aws

This project creates a basic REST API using AWS Lambda and API Gateway. It demonstrates serverless architecture and allows you to deploy a simple API endpoint that responds with JSON. The project will help you practice working with AWS Lambda, API Gateway, and their integration.

Steps:
Set Up AWS Lambda Function:

Go to the AWS Management Console and navigate to Lambda.
Create a new Lambda function using Python as the runtime.
Inside the Lambda function, write a simple script that returns a JSON response.
Example Lambda function code:

python
Copy code
import json

def lambda_handler(event, context):
    response = {
        'statusCode': 200,
        'body': json.dumps({
            'message': 'Hello from Lambda!',
            'input': event
        })
    }
    return response
Create an API Gateway:

In the AWS Management Console, go to API Gateway and create a new REST API.
Set up a new resource and method (GET or POST) and link it to the Lambda function you created.
Deploy the API to a stage (e.g., dev).
Test the API:

Once the API is deployed, you'll get a public endpoint (URL).
Test the API using curl, Postman, or a web browser to see if the Lambda function responds correctly.
Example request using curl:

bash
Copy code
curl https://your-api-endpoint.amazonaws.com/dev/resource
Add a Local Python Script to Call the API:

You can also create a simple Python script to send a GET request to your API.
python
Copy code
import requests

url = "https://your-api-endpoint.amazonaws.com/dev/resource"
response = requests.get(url)

print(response.status_code)
print(response.json())
