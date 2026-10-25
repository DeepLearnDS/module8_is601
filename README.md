# Module 8: Build and Test Your First Web Application with FastAPI
Dockerhub URL:
https://hub.docker.com/repository/docker/codeec/601_module8/general

## Project Overview

This project enhances a FastAPI-based calculator web application by implementing unit, integration, and end-to-end (E2E) tests. It also incorporates application logging and continuous integration (CI) using GitHub Actions.

The application allows users to perform basic arithmetic operations through a web interface and verifies their functionality through automated testing.

## Objectives

- Build and run a FastAPI calculator web application.
- Implement unit tests for arithmetic operations.
- Implement integration tests for API endpoints.
- Implement end-to-end tests using Playwright.
- Add logging to track application operations and errors.
- Configure GitHub Actions to automatically run tests on code pushes.

## Features

- **FastAPI Web Application:** Provides a web interface for the calculator.
- **Arithmetic Operations:** Supports addition, subtraction, multiplication, and division.
- **Error Handling:** Handles division by zero and invalid requests.
- **Unit Testing:** Tests the individual arithmetic operations.
- **Integration Testing:** Tests API endpoints and their responses.
- **End-to-End Testing:** Uses Playwright to simulate user interactions with the calculator.
- **Logging:** Records application activity and errors.
- **Continuous Integration:** Runs automated tests through GitHub Actions.

## Technologies Used

- Python 3.12
- FastAPI
- Uvicorn
- Pydantic
- Pytest
- Playwright
- HTML, CSS, and JavaScript
- Git and GitHub
- GitHub Actions
- Docker and Docker Compose

## Project Structure

```text
module8_is601/
├── .github/
│   └── workflows/
│       └── ...
├── app/
│   └── operations/
│       └── __init__.py
├── templates/
│   └── index.html
├── tests/
│   ├── unit/
│   │   └── test_calculator.py
│   ├── integration/
│   │   └── test_fastapi_calculator.py
│   ├── e2e/
│   │   └── test_e2e.py
│   └── conftest.py
├── main.py
├── requirements.txt
├── pytest.ini
├── Dockerfile
├── docker-compose.yml
└── README.md
```

*Note: The structure above illustrates the main project files. The exact workflow filename and additional files may vary.*

## Installation and Setup

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd module8_is601
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your repository URL.

### 2. Create and activate a virtual environment

On Ubuntu or Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Install Playwright browsers and dependencies

```bash
playwright install
playwright install-deps
```

These commands install the browsers and required system libraries for end-to-end testing on supported Linux environments.

## Running the Application

Start the FastAPI development server:

```bash
uvicorn main:app --reload --host 127.0.0.1 --port 8000
```

Open the application in a browser:

http://localhost:8000

Enter two numbers and select an arithmetic operation to view the result.

## Running the Tests

Run the complete test suite:

```bash
pytest
```

Run specific test categories:

**Unit tests**

```bash
pytest tests/unit/
```

**Integration tests**

```bash
pytest tests/integration/
```

**End-to-end tests**

```bash
pytest tests/e2e/
```

The tests verify arithmetic operations, API responses, browser interactions, and error handling.

## Logging and Error Handling

The application uses Python's logging module to record application events and errors. FastAPI exception handlers return appropriate JSON error responses for HTTP exceptions and request validation errors.

Division by zero is handled with an error response rather than returning a normal calculation result.

## Continuous Integration with GitHub Actions

GitHub Actions is configured to run automated tests when code is pushed to the repository. This helps verify that the application and its tests continue to work as changes are made.

The workflow results can be viewed in the **Actions** tab of the GitHub repository.

## Docker

The project includes Docker configuration for building and running the application in a container.

To build and start the application using Docker Compose:

```bash
docker compose up --build
```

Stop the running containers with `Ctrl + C`.

## Test Results

The local test suite completed successfully with **29 tests passed**.

The test suite includes:
- Unit tests for arithmetic operations.
- Integration tests for FastAPI endpoints.
- End-to-end tests for the calculator web interface and division-by-zero handling.

## Assignment Deliverables

- GitHub repository containing the application code, tests, dependencies, and GitHub Actions workflow.
- Screenshot of a successful GitHub Actions workflow run.
- Screenshot of the calculator application running in a web browser.

## Conclusion

This project demonstrates the development and testing of a FastAPI web application using automated testing, logging, version control, and continuous integration. It provides practice in verifying application functionality at the unit, integration, and end-to-end levels.
