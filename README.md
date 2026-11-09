# Daily Habit and Task Tracker

An AI-enhanced productivity application designed to manage daily habits, organize tasks, and provide proactive motivational insights. Features a modular Flask backend and a responsive web dashboard styled with TailwindCSS.

## Overview

The Daily Habit & Task Tracker provides an integrated environment for building consistent routines and managing daily deliverables. It combines structured SQLite data storage, service-oriented business logic, and an AI advisory service powered by OpenRouter / Claude.

## Features

### Habit Tracking
- Daily habit creation with recurrence tracking.
- Completion logging with automated streak calculation.
- Historical habit performance metrics.

### Task Management
- Task organization with priority tags.
- Direct completion toggling and dynamic filtering.
- Daily workload overview and pending action items.

### AI Assistant Layer
- **Personalized Motivation**: Context-aware greetings based on daily consistency.
- **Habit Insights**: Pattern recognition and consistency analytics.
- **Smart Prioritization**: Intelligent ordering suggestions for daily tasks.
- **Habit Recommendations**: Suggestions for new routines based on existing habits.

### Modern Web Interface
- Responsive dashboard layout built with Flask and TailwindCSS.
- Real-time updates for habits, tasks, and analytical metrics.
- Modal dialogues, action toasts, and clear visual indicators.

## Project Structure

```text
Daily-habit-tracker/
├── requirements.txt            # Python dependencies
├── data.json                   # Legacy data format / migration export
├── README.md                   # Project documentation
│
└── backend/                    # Core application service
    ├── app.py                  # Application entry point
    ├── wsgi.py                 # WSGI entry point for production
    ├── config.py               # Environment and application configuration
    ├── database.py             # Database connection and schema initialization
    ├── models.py               # Data models (Habit, Task, Completion)
    ├── services.py             # Business logic services (HabitService, TaskService)
    ├── ai_service.py           # AI integration layer (OpenRouter / Claude)
    ├── app/                    # Application package modules
    ├── static/                 # Static assets (CSS, JavaScript)
    ├── templates/              # Jinja2 dashboard templates
    └── tests/                  # Automated test suites
```

## Getting Started

### Prerequisites
- Python 3.9 or higher
- Git

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/K4l1C0d3x/Daily-habit-tracker.git
   cd Daily-habit-tracker
   ```

2. **Set up a virtual environment**:
   ```bash
   # Windows
   python -m venv .venv
   .venv\Scripts\activate

   # macOS / Linux
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Configuration**:
   Create a `.env` file in the root or `backend/` directory:
   ```env
   OPENROUTER_API_KEY=your_openrouter_api_key
   # or
   ANTHROPIC_API_KEY=your_anthropic_api_key
   ```

### Running the Application

Launch the Flask development server:

```bash
cd backend
python app.py
```

Access the dashboard at `http://localhost:5000`.

## Testing

Run the test suite using `pytest`:

```bash
pytest backend/tests
```

## Architecture and Customization

- **Service Layer**: Core data interactions reside in `backend/services.py`, separating business logic from route definitions.
- **Data Models**: Relational schemas for habits, tasks, and streaks are defined in `backend/models.py`.
- **AI Integrations**: Prompt engineering and API clients are managed in `backend/ai_service.py`.
- **UI Customization**: Frontend views and TailwindCSS styles are located in `backend/templates/` and `backend/static/`.

## Deployment

For production deployments, execute with a production WSGI HTTP server:

```bash
gunicorn --bind 0.0.0.0:5000 backend.wsgi:app
```

## Contributing

1. Fork the repository.
2. Create a dedicated feature branch.
3. Commit your changes with clear messages.
4. Verify tests pass and submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Developed by **kalidas kj**
- UI Icons by [Lucide](https://lucide.dev/)
- CSS Framework: [TailwindCSS](https://tailwindcss.com/)
- AI integration powered by OpenRouter / Claude
