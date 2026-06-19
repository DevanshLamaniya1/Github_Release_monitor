# GitHub Release Monitor

A FastAPI-based application that monitors GitHub repositories for new releases and automatically sends email notifications to subscribed users. The project is built with production-oriented practices including Docker, CI/CD, code quality checks, and database integration.

## Features

* Monitor GitHub repositories for new releases
* Store repository and release information in a database
* Send email notifications when a new release is detected
* REST API built with FastAPI
* Database integration using SQLAlchemy and Supabase
* Dockerized application for easy deployment
* Automated code quality checks with Black, Flake8, and pre-commit
* CI/CD pipeline using GitHub Actions
* Environment-based configuration management

## Tech Stack

### Backend

* Python
* FastAPI
* SQLAlchemy

### Database

* Supabase (PostgreSQL)

### DevOps & Automation

* Docker
* GitHub Actions (CI/CD)

### Code Quality

* Black
* Flake8
* pre-commit

### External Services

* GitHub API
* Email Service

## Architecture

```text
GitHub API
     |
     v
GitHub Release Monitor
     |
     +--> SQLAlchemy
     |       |
     |       v
     |   Supabase/PostgreSQL
     |
     +--> Email Notification Service
```

## Project Structure

```text
github-release-monitor/
│
├── app/
│   ├── api/
│   ├── models/
│   ├── services/
│   ├── database/
│   ├── utils/
│   └── main.py
│
├── tests/
│
├── .github/
│   └── workflows/
│
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── .env.example
├── .pre-commit-config.yaml
└── README.md
```

## Installation

### Clone the Repository

```bash
git clone https://github.com/your-username/github-release-monitor.git
cd github-release-monitor
```

### Create Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Linux/macOS**

```bash
source venv/bin/activate
```

**Windows**

```bash
venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

## Environment Variables

Create a `.env` file in the project root.

```env
DATABASE_URL=your_database_url

GITHUB_TOKEN=your_github_token

SMTP_HOST=smtp.example.com
SMTP_PORT=587
SMTP_USERNAME=your_email
SMTP_PASSWORD=your_password

EMAIL_FROM=your_email@example.com
```

## Running the Application

### Local Development

```bash
uvicorn app.main:app --reload
```

Application will be available at:

```text
http://localhost:8000
```

API Documentation:

```text
http://localhost:8000/docs
```

## Running with Docker

Build the image:

```bash
docker build -t github-release-monitor .
```

Run the container:

```bash
docker run -p 8000:8000 github-release-monitor
```

Or use Docker Compose:

```bash
docker-compose up --build
```

## Code Quality

### Format Code

```bash
black .
```

### Lint Code

```bash
flake8 .
```

### Run Pre-commit Hooks

```bash
pre-commit run --all-files
```

## CI/CD

The project uses GitHub Actions for:

* Automated testing
* Linting
* Code formatting checks
* Build validation
* Continuous Integration

Workflows are located in:

```text
.github/workflows/
```

## API Endpoints

### Repositories

| Method | Endpoint           | Description       |
| ------ | ------------------ | ----------------- |
| POST   | /repositories      | Add repository    |
| GET    | /repositories      | List repositories |
| DELETE | /repositories/{id} | Remove repository |

### Releases

| Method | Endpoint         | Description           |
| ------ | ---------------- | --------------------- |
| GET    | /releases        | List tracked releases |
| GET    | /releases/latest | Get latest releases   |

### Notifications

| Method | Endpoint               | Description          |
| ------ | ---------------------- | -------------------- |
| POST   | /notifications/send    | Send notification    |
| GET    | /notifications/history | Notification history |

## Future Improvements

* User authentication and authorization
* GitHub Webhook support
* Background task scheduling
* Retry mechanism for failed notifications
* Unit and integration testing
* Monitoring and observability
* Multi-channel notifications (Slack, Discord, Telegram)
* Kubernetes deployment

## Learning Outcomes

This project demonstrates:

* REST API development with FastAPI
* Database modeling with SQLAlchemy
* PostgreSQL/Supabase integration
* Third-party API integration
* Email automation
* Docker containerization
* CI/CD implementation
* Python code quality tooling
* Production-ready backend development practices

## License

This project is licensed under the MIT License.

## Author

Your Name

GitHub: https://github.com/devanshlamaniya1

