```markdown
# Tasks README

This repository contains a project aimed at implementing basic authentication functionalities in a Flask API. Below are the steps and explanations on how to set up, configure, and use the provided functionalities.

## Setup and Start Server
1. Clone the repository:
   ```
   git clone https://github.com/alx-backend-user-data/0x01-Basic_authentication.git
   ```

2. Navigate to the project directory:
   ```
   cd 0x01-Basic_authentication
   ```

3. Install required dependencies:
   ```
   pip3 install -r requirements.txt
   ```

4. Start the server:
   ```
   API_HOST=0.0.0.0 API_PORT=5000 python3 -m api.v1.app
   ```

## Error Handlers
### Unauthorized (401)
- HTTP status code for unauthorized request: 401
- Add a new error handler in `api/v1/app.py` to handle 401 errors.
- Test the new error handler by accessing the endpoint `/api/v1/unauthorized`.

### Forbidden (403)
- HTTP status code for unauthorized access to a resource: 403
- Add a new error handler in `api/v1/app.py` to handle 403 errors.
- Test the new error handler by accessing the endpoint `/api/v1/forbidden`.

## Auth Class
- Create a class `Auth` to manage API authentication.
- Implement methods for requiring authentication, handling authorization headers, and retrieving current user.
- Test the `Auth` class using provided scripts.

## Define Routes Without Authentication
- Update the `require_auth` method in the `Auth` class to define routes that don't need authentication.
- Test the updated method using provided scripts.

## Request Validation
- Implement request validation to secure the API.
- Use Flask's `before_request` method to filter each request.
- Ensure proper handling of authentication errors.

## Basic Auth
- Implement basic authentication by creating a `BasicAuth` class.
- Configure the API to use `BasicAuth` based on the `AUTH_TYPE` environment variable.
- Test basic authentication using provided scripts.

## Basic - Base64 Part
- Add methods to handle extraction and decoding of the Base64 part of the Authorization header for Basic Authentication.
- Test the methods using provided scripts.

## Basic - User Credentials
- Implement methods to extract user credentials from Base64 decoded authorization headers.
- Test the methods using provided scripts.

## Basic - User Object
- Implement a method to retrieve the User instance based on email and password.
- Ensure proper handling of different scenarios and edge cases.
- Test the method using provided scripts.

## Basic - Overload current_user
- Implement method to retrieve the User instance for a request using Basic Authentication.
- Ensure integration of all previously implemented functionalities.
- Test the complete Basic Authentication setup.

## Advanced Tasks
- Advanced tasks include allowing passwords with ":" and requiring auth with "*" in excluded paths.
- Follow provided instructions and test scripts for each advanced task.

---

Feel free to explore the codebase further and make any necessary adjustments based on your requirements.

For any issues or inquiries, please refer to the GitHub repository or contact the project maintainers.
```
