# Library-Management-System-Project

This project encapsulates the development of a **Library Management System** leveraging the Flask framework and deployed via Gunicorn. It offers robust functionalities for the systematic administration of bibliographic resources, user management, and lending operations.

---

## Features

- Implementation of user authentication with role-based access control (Administrator/User).
- Comprehensive CRUD operations for managing books, users, and transaction records.
- Fully responsive web interface designed for optimal usability.
- Advanced search and filtering capabilities, enabling queries by title, author, or genre.
- Real-time tracking of book availability and borrowing histories.

---

## Getting Started

### Prerequisites

1. **Python** (Version 3.8 or later)
2. **pip** (Python package management tool)
3. **Virtualenv** (Recommended for environment isolation)

---

### Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/<your_username>/library-management-system.git
   cd library-management-system
   ```

2. **Establish a Virtual Environment:** (Recommended for dependency management)
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Execute the Application Locally:**
   ```bash
   flask run
   ```
   The application interface will be accessible at `http://127.0.0.1:5000/`.

---

### Deployment with Gunicorn

1. **Install Gunicorn:**
   ```bash
   pip install gunicorn
   ```

2. **Deploy the Application Using Gunicorn:**
   ```bash
  
   gunicorn wsgi:app --bind 0.0.0.0:8000
   ```
  
3. **Optional: Configure a Process Manager:**
   Employ a process manager such as **systemd** to oversee the Gunicorn service in a production environment.

---

## Folder Structure

```
.
├── app/
│   ├── __init__.py        # Application factory
│   ├── models.py          # Database models
│   ├── routes.py          # Application routes
│   ├── templates/         # HTML templates
│   └── static/            # Static files (CSS, JS, images)
├── wsgi.py                 # Entry point for development
└── README.md              # Project documentation
```

---

## Environment Variables

Define critical application settings in a `.env` file located in the root directory:

```
FLASK_APP=run.py
FLASK_ENV=development
DATABASE_URL=sqlite:///library.db  # Replace with the desired database URL
SECRET_KEY=your_secret_key_here
```

---

## Testing

Execute the testing suite using:
```bash
pytest
```
It is imperative to ensure all tests pass prior to production deployment.

---

## Acknowledgments

- Flask Framework: [Flask](https://flask.palletsprojects.com/)
- Gunicorn WSGI Server: [Gunicorn](https://gunicorn.org/)

