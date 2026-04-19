# Career Path Learning Platform - Django Version

A comprehensive Django-based web application for personalized career path exploration with interactive quizzes, career roadmaps, and AI-powered recommendation engine.

## 🚀 Features

- User Authentication
- Profile Management
- Interactive Quizzes
- Career Paths
- Recommendations Engine
- Progress Tracking
- Admin Dashboard

## 🛠️ Tools & Technologies

- Python 3.8+
- Django
- Django REST framework
- SQLite (default, can be changed to PostgreSQL/MySQL)
- HTML/CSS/JavaScript for frontend templates
- Git for version control
- GitHub for source repository and remote
- Virtualenv for isolated environment

## 📁 Project Structure

- `careerplatform/`: Django project settings and URL config
- `careers/`: Career path data, models, views, templates
- `quizzes/`: Quiz models, view logic, templates, and scoring
- `recommendations/`: Recommendation engine, user match logic, views
- `games/`: Gamification, leaderboard, and game logic
- `users/`: Authentication, profile management
- `templates/`: Base and app-specific templates
- `static/`: CSS/JS/images

## ⚙️ Setup and Local Development

1. `git clone https://github.com/manishthavisi/career-platform-django.git`
2. `cd career-platform-django`
3. `python -m venv venv`
4. `venv\Scripts\activate` (Windows) or `source venv/bin/activate` (macOS/Linux)
5. `pip install -r requirements.txt`
6. `python manage.py migrate`
7. `python manage.py createsuperuser` (optional)
8. `python manage.py runserver`

Open http://localhost:8000 in browser.

## 🧪 Seed Data (Optional)

- `python manage.py seed_careers`
- `python manage.py seed_quizzes`
- `python manage.py seed_recommendations`

## 💾 Database

- Default: SQLite at `db.sqlite3`
- To change, update `careerplatform/settings.py` DATABASES block for PostgreSQL or MySQL.

## 🔐 Security and Best Practices

- Enable `DEBUG = False` in production
- Set `ALLOWED_HOSTS` in settings
- Use environment variables for `SECRET_KEY` and DB credentials
- Use SSL for production server
- Set up production-ready web server (Gunicorn + Nginx)

## 📦 Deployment Notes

- Configure static files with `python manage.py collectstatic`
- Use `whitenoise` or cloud storage for static media
- Run migrations on deploy: `python manage.py migrate`

## 🧩 Contributions

Feel free to open issues, submit PRs, and improve features. This project is open source and designed for collaborative development.
