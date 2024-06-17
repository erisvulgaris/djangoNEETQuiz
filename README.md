
# QuizAppBackend

This is the backend for the Quiz App, built using Django and Django REST Framework. It provides APIs for managing quiz categories, subjects, units, topics, questions, and quiz sessions.

## Table of Contents

- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Loading Questions](#loading-questions)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/QuizappBackend.git
    cd QuizappBackend
    ```

2. Create and activate a virtual environment:

    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```

3. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

## Configuration

1. Copy `example.env` to `.env` and update the environment variables as needed:

    ```bash
    cp example.env .env
    ```

2. Set up your database configuration in `settings.py` or in the `.env` file.

## Running the Application

1. Apply the migrations:

    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

2. Create a superuser for accessing the Django admin:

    ```bash
    python manage.py createsuperuser
    ```

3. Start the development server:

    ```bash
    python manage.py runserver
    ```

4. Access the admin interface at `http://127.0.0.1:8000/admin`.

## Loading Questions

To load questions into the database from a JSON file, use the custom management command `load_questions`:

```bash
python manage.py load_questions path/to/your/questions.json
```

The JSON file should have the following format:

```json
[
    {
        "unique_id": "q1",
        "question": "What is the capital of France?",
        "difficulty_level": "easy",
        "quiz_type": "multiple_choice",
        "explanation": "The capital of France is Paris.",
        "option_a": "Paris",
        "option_b": "London",
        "option_c": "Berlin",
        "option_d": "Madrid",
        "answer": "A",
        "topic_name": "Geography >> Europe >> Capitals"
    },
    ...
]
```

## API Endpoints

The Quiz App backend provides the following API endpoints:

- `GET /api/categories/`: List all categories.
- `GET /api/subjects/`: List all subjects.
- `GET /api/units/`: List all units.
- `GET /api/topics/`: List all topics.
- `GET /api/questions/`: List all questions.
- `GET /api/quiz-sessions/`: List all quiz sessions.
- `POST /api/attempts/`: Submit a quiz attempt.
- `GET /api/leaderboard/`: Get the leaderboard.

## Contributing

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Make your changes and commit them with a descriptive message.
4. Push your changes to your fork and create a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

