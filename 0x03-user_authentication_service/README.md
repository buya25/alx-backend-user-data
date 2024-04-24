# Tasks Project README

## Project Overview
This project focuses on building a user authentication service using Python, Flask, and SQLAlchemy. It involves creating a SQLAlchemy model for users, implementing various functionalities such as user registration, login, session management, password reset, and user profile access, all through HTTP endpoints.

## Project Structure
The project is organized into several tasks, each addressing a specific aspect of the user authentication service. Below is an overview of each task along with its purpose:

### Task 0: User Model
Define a SQLAlchemy model named User with attributes such as id, email, hashed_password, session_id, and reset_token.

### Task 1: Create User
Implement a method to add a user to the database with provided email and hashed_password.

### Task 2: Find User
Implement a method to find a user in the database based on arbitrary keyword arguments.

### Task 3: Update User
Implement a method to update a user's attributes in the database.

### Task 4: Hash Password
Define a method to hash passwords securely using bcrypt.

### Task 5: Register User
Implement user registration functionality, including checking for existing users and hashing passwords.

### Task 6: Basic Flask App
Set up a basic Flask app with a single GET route ("/") returning a JSON message.

### Task 7: Register User Endpoint
Implement an endpoint to register users via HTTP POST requests.

### Task 8: Credentials Validation
Implement a method to validate user credentials during login.

### Task 9: Generate UUIDs
Implement a method to generate UUIDs for various purposes.

### Task 10: Get Session ID
Create a method to generate session IDs for users.

### Task 11: Log In
Implement a login function to handle user authentication via HTTP POST requests.

### Task 12: Find User by Session ID
Implement a method to find a user based on their session ID.

### Task 13: Destroy Session
Implement a method to destroy a user's session by setting their session ID to None.

### Task 14: Log Out
Implement a logout function to handle user logout via HTTP DELETE requests.

### Task 15: User Profile
Implement a function to retrieve a user's profile information via HTTP GET requests.

### Task 16: Generate Reset Password Token
Implement a method to generate reset password tokens for users.

### Task 17: Get Reset Password Token
Implement an endpoint to retrieve reset password tokens via HTTP POST requests.

### Task 18: Update Password
Implement a method to update a user's password using a reset token.

### Task 19: Update Password Endpoint
Implement an endpoint to update user passwords via HTTP PUT requests.

## Usage
To run the project, follow these steps:
1. Clone the GitHub repository: [alx-backend-user-data](https://github.com/username/alx-backend-user-data)
2. Navigate to the appropriate directory (`0x03-user_authentication_service`).
3. Execute the main Python file corresponding to the task you want to test.

## Running Tests
To test each functionality, execute the provided main Python file for the respective task. The file contains sample usage scenarios and expected outputs.

## Contributors
- [Yabs Mullo] (https://github.com/buya25)

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
