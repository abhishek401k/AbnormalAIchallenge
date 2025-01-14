# Secure File Sharing Application

A web application designed for secure file sharing with user authentication, file encryption, and shareable links with expiration.

## Features

- **User Authentication**: Registration, login with multi-factor authentication.
- **File Management**: Upload, encrypt, and manage files.
- **Secure Sharing**: Generate shareable links with an expiration time.
- **Frontend**: React-based UI with Redux for state management.
- **Backend**: Django REST Framework for API, with JWT for authentication.
- **Dockerized**: For easy deployment and consistency across different environments.

## Getting Started

### Prerequisites

- Docker
- Docker Compose

### Installation

1. **Clone the Repository**

   ```bash
   git clone [Your Repo URL]
   cd secure-file-sharing

2.**Build and Run Containers**
Navigate to the project directory and use Docker Compose to build and run the application:

   ```bash
   docker-compose up --build
   ```

This command will:
- Start PostgreSQL for the backend database.
- Build and run the Django backend.
- Build and run the React frontend served by Nginx.

## Usage
-Backend: Access the Django admin at http://localhost:8000/admin/ (if you've set up admin credentials).
-Frontend: Visit http://localhost:3000/ to interact with the UI.

Configuration
Environment Variables: Sensitive configurations are managed through environment variables in ```docker-compose.yml```. Ensure ```SECRET_KEY``` for Django is securely set before production use.
Database: The application uses PostgreSQL. Connection details are managed in the Docker Compose file.

**Project Structure**
```
secure-file-sharing/
├── docker-compose.yml
├── file-sharing-client/     # React Frontend
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── store/
│   │   ├── App.js
│   │   └── index.js
│   ├── Dockerfile
│   └── package.json
└── file_sharing_app/       # Django Backend
    ├── api/
    │   ├── migrations/
    │   ├── __init__.py
    │   ├── admin.py
    │   ├── apps.py
    │   ├── models.py
    │   ├── serializers.py
    │   ├── tests.py
    │   ├── urls.py
    │   └── views.py
    ├── file_sharing_app/
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    ├── manage.py
    ├── Dockerfile
    └── requirements.txt
```
**Development**
## Frontend
Run `npm install` to install dependencies within the `file-sharing-client directory`.
Development server: `npm start` inside file-sharing-client.

## Backend
Inside **file_sharing_app**, you can `run python manage.py runserver` for local development if not using Docker.

## Docker Development
For changes in either frontend or backend, rebuild the Docker images with:
`docker-compose up --build`

**Security Considerations**
**SSL/TLS**: Ensure production environments use HTTPS.
**Password Hashing**: Using `bcrypt` for password security.
**JWT**: For stateless authentication.
**CORS**: Configured in Django settings for frontend-backend communication.

**Contributing**
-Fork the repository.
-Create your feature branch (`git checkout -b feature/AmazingFeature`).
-Commit your changes (`git commit -m 'Add some AmazingFeature`).
-Push to the branch (`git push origin feature/AmazingFeature`).
-Open a Pull Request.



Acknowledgments
Thanks to all contributors and open-source projects that have made this possible.


