# Simple Djoser Project with DRF and Token Authentication
This project is a basic implementation of user authentication using Django, Django REST Framework (DRF), and Djoser. 
Using the Djoser library for Django, the provided URL patterns will set up a variety of endpoints for handling authentication-related tasks. 
The djoser.urls and djoser.urls.authtoken modules include many endpoints for managing users and authentication tokens.

Setup Instructions

  ->Clone the Project-Create a directory, open a terminal in the directory path, and clone the  project:

      git clone https://github.com/abynxv/Djoser-DRF.git
  ->Install Virtual Environment
  
      pip install virtualenv
      
  ->Create a virtual environment within the directory:

      python -m venv venv_name  # On Windows
      python3 -m venv venv_name  # On macOS/Linux

  ->Activate Virtual Environment

      venv_name\Scripts\activate       # On Windows
      source venv_name/bin/activate    # On macOS/Linux

  ->Install Requirements

      pip install django djangorestframework djoser

  ->Open the project in VS Code:

      code .

  ->Open a terminal in VS Code, navigate to the project directory, and run the server:
  
      cd myproject
      python manage.py runserver
      
Djoser Endpoints

1.Register

    Endpoint  : http://localhost:8000/auth/users/
    Method    : POST     - Register User
    Data      : JSON     - {"name": "string", "email": "email", "password": "password"}
    
2.Activate the User (if needed)

    Endpoint  : http://localhost:8000/auth/users/activation/
    Method    : POST     - Activate the User
    Data      : JSON     - {"uid": "<uid>","token": "<token>"}
    
3.Obtain a Token

    Endpoint  : http://localhost:8000/auth/token/login/
    Method    : POST     - Obtain a Token
    Data      : JSON     - {"username": "testuser","password": "testpassword"}
    Expected Response    - {"auth_token": "your_generated_token"}
    
4.Get Current User Profile

    Endpoint  : http://localhost:8000/auth/users/me/
    Method    : GET      - Get Current User Profile
    Headers   - Key   :  Authorization
                Value :  Token your_generated_token
                
5.Set Password

    Endpoint  : http://localhost:8000/auth/users/set_password/
    Method    : POST     - Set Password
    Headers   - Key   :  Authorization
                Value :  Token your_generated_token

6.Reset Password

    Endpoint  : http://localhost:8000/auth/users/reset_password/
    Method    : POST     - Reset Password
    Headers   - Key   :  Authorization
                Value :  Token your_generated_token

7.Reset Password Confirm

    Endpoint  : http://localhost:8000/auth/users/reset_password_confirm/
    Method    : POST     - Reset Password Confirm
    Headers   - Key   :  Authorization
                Value :  Token your_generated_token

8.Login

    Endpoint  : http://localhost:8000/auth/token/login/
    Method    : POST     - Login
    Headers   - Key   :  Authorization
                Value :  Token your_generated_token

9.Logout

    Endpoint  : http://localhost:8000/auth/token/logout/
    Method    : POST     - Logout
    Headers   - Key   :  Authorization
                Value :  Token your_generated_token

10.Current User

    Method    : GET   /auth/users/me/ - Get the current authenticated user's information.
                PUT   /auth/users/me/ - Update the current authenticated user's information.
                PATCH /auth/users/me/ - Partially update the current authenticated user's information.
    Headers   - Key   :  Authorization
                Value :  Token your_generated_token
