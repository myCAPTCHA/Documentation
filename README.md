# myCAPTCHA API Documentation

## Overview
The myCAPTCHA API provides a simple interface for generating and validating captchas to protect against automated access. It includes endpoints for creating an API key, serving a captcha, and validating user responses.

## Base URL
The base URL for all API endpoints is `https://api.mycaptcha.org`.


## Endpoints

### GET /api_key
- Description: Generates a new API key that can be used to authenticate requests to other endpoints.
- Response: JSON object containing the newly generated API key.

### GET /captcha
- Description: Serves a random captcha image encoded in base64 along with a unique code for validation purposes.
- Parameters: Requires an `api_key` query parameter for authentication.
- Response: JSON object containing the captcha code and the data URL of the captcha image.

### POST /validate_captcha
- Description: Validates the user's response to a captcha challenge.
- Parameters: JSON payload containing `code` (the captcha code) and `answer` (the user's response).
- Response: JSON object indicating whether the response was valid or not.

## Usage
To use the API, clients must first obtain an API key by accessing the `/api_key` endpoint. This key must then be included in requests to the `/captcha` endpoint to retrieve a captcha challenge. Finally, responses can be validated through the `/validate_captcha` endpoint by submitting the captcha code and the user's answer.

## Error Handling
The API uses standard HTTP status codes to indicate the success or failure of requests. Clients should handle these responses accordingly to implement robust error handling in their applications.
