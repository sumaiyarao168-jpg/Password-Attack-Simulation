# Password-Attack-Simulation
Flask Login System with Basic Rate Limiting

A lightweight Flask application demonstrating user authentication with simple IP-based rate limiting. This project is intended for educational purposes to illustrate authentication flow, HTTP status codes, and defensive controls against repeated failed login attempts.

Features

- Secure login endpoint using HTTP POST
- Username and password authentication
- IP-based failed login tracking
- Automatic blocking after a configurable number of failed attempts
- Appropriate HTTP status codes ("200", "401", "429")
- Simple client script for testing the API

Tech Stack

- Python 3
- Flask
- Requests

Project Structure

.
├── app.py          # Flask application
├── client.py       # API testing client
├── requirements.txt
└── README.md

Installation

Clone the repository:

git clone https://github.com/your-username/flask-login-system.git
cd flask-login-system

Install the required packages:

pip install -r requirements.txt

Or install them directly:

pip install flask requests

Running the Application

Start the Flask server:

python app.py

The application will be available at:

http://127.0.0.1:5000

API Endpoint

POST "/login"

Request Parameters

Parameter| Type| Description
username| String| Username
password| String| Password

Example request:

username=admin
password=admin123

Response Codes

Status Code| Description
200| Login successful
401| Invalid credentials
429| Too many failed login attempts

Example Response

Successful login:

Welcome Admin!

Failed login:

Invalid Credentials!

Rate limit exceeded:

Too Many Attempts! Try Again Later.

Security Notes

This project is intended for learning and demonstration purposes. It intentionally keeps the implementation simple. A production-ready authentication system should include:

- Password hashing (e.g., Werkzeug or bcrypt)
- Database-backed user storage
- Session management
- CSRF protection where applicable
- Persistent rate limiting (e.g., Redis)
- HTTPS
- Production WSGI server (Gunicorn/uWSGI)

Disclaimer

This repository is provided solely for educational purposes to demonstrate Flask authentication and basic rate-limiting concepts. It should not be used as-is in production environments.

License

This project is licensed under the MIT License.