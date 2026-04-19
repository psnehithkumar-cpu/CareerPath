# Career Path Learning Platform - Django Version

A comprehensive Django-based web application for personalized career path exploration with interactive quizzes, career roadmaps, and AI-powered recommendation engine.

## 🚀 Features

- **User Authentication**: Secure registration and login system
- **Profile Management**: Users can set skills, interests, and experience level
- **Interactive Quizzes**: Take assessments in skills, interests, and learning styles
- **Career Paths**: Explore 5+ detailed career paths with roadmaps and requirements
- **Recommendations Engine**: Get personalized career recommendations based on profile
- **Progress Tracking**: Monitor progress through career roadmap phases
- **Admin Dashboard**: Manage users, quizzes, and career data through Django Admin

## 📋 Prerequisites

- Python 3.8+
- pip (Python package installer)
- Virtual environment (recommended)

## 🛠️ Installation

### 1. Clone or Download the Project

```bash
cd career-platform-django
```

### 2. Create Virtual Environment

```bash
python -m venv venv
```

### 3. Activate Virtual Environment

**On Windows:**
```bash
.\venv\Scripts\Activate.ps1
```

**On macOS/Linux:**
```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install django djangorestframework django-cors-headers python-dotenv pillow
```

## 🔧 Setup & Configuration

### 1. Create Database

```bash
python manage.py makemigrations
python manage.py migrate
```

### 2. Create Superuser (Admin)

```bash
python manage.py createsuperuser
```

Or use the default credentials:
- Username: `admin`
- Password: `admin123`
- Email: `admin@example.com`

### 3. Seed Sample Data

Load sample career paths:
```bash
python manage.py seed_careers
```

Load sample quizzes:
```bash
python manage.py seed_quizzes
```

## 🚀 Running the Application

### Start Development Server

```bash
python manage.py runserver
```

The application will be available at: **http://localhost:8000**

### Access Admin Panel

Navigate to: **http://localhost:8000/admin**
- Username: `admin`
- Password: `admin123`

## 📱 Features & Navigation

### Home Page
- Landing page with feature overview
- Quick access to registration/login
- Call-to-action buttons

### Authentication
- **Register**: Create new account with username, email, password
- **Login**: Authenticate with credentials
- **Profile**: Update personal and career information

### Dashboard
- Overview of profile completion
- Quick action cards
- Access to all features

### Quizzes
- **Quiz Center**: Browse all available quizzes
- **Take Quizzes**: Answer questions about skills, interests, learning style
- **Track Results**: View quiz scores and completion status

### Career Paths
- **Explore Careers**: Browse 5 featured career paths:
  - Full Stack Developer
  - Data Scientist
  - Product Manager
  - UI/UX Designer
  - DevOps Engineer
- **Career Details**: View salary, requirements, roadmap, resources
- **Track Progress**: Monitor progress through 3-phase career roadmaps

### Recommendations
- **Get Recommendations**: Receive personalized career matches
- **Match Scoring**: View detailed score breakdown:
  - Skills Match (40%)
  - Interests Match (40%)
  - Experience Match (20%)
- **Ranked Results**: Careers sorted by match percentage

## 🗄️ Database Models

### User (Custom)
- Extended Django User model
- Skills (JSON array)
- Interests (JSON array)
- Experience years
- Quiz scores
- Profile image support

### Quiz
- Questions with multiple types
- Categories: Skills, Interests, Learning Style
- Question types: Multiple choice, Rating, Text

### CareerPath
- Career information and description
- Salary range and job outlook
- 3-phase roadmaps with descriptions
- Required skills and education
- Company examples and learning resources

### Recommendation
- User-career path matches
- Weighted scoring (40-40-20)
- Match breakdown percentages
- Reasoning and timestamps

### CareerProgress
- Track user progress on career paths
- Current phase and completion percentage
- Started date tracking

## 🎨 Architecture

### Frontend
- Django Templates with Jinja2
- Responsive CSS3 (Flexbox, Grid)
- Modern gradient design
- Mobile-friendly interface

### Backend
- Django 6.0.2
- SQLite database (default)
- RESTful views and templates
- Authentication with Django sessions

### Styling
- Custom CSS with variables
- Gradient backgrounds
- Card-based layouts
- Smooth transitions

## 📊 Recommendation Algorithm

The system uses a rule-based weighted scoring approach:

```
Final Score = (Skills Match × 0.4) + (Interests Match × 0.4) + (Experience Match × 0.2)
```

**Skills Match**: Overlap between user skills and required skills
**Interests Match**: Alignment with suggested interests
**Experience Match**: Years of experience vs. requirement

## 🔐 Security Features

- Password hashing with Django's built-in system
- CSRF protection on all forms
- Login required decorators on protected views
- SQL injection prevention through ORM
- Secure session management

## 📧 User Workflows

### New User Flow
1. Register with username, email, password
2. Complete profile (skills, interests, experience)
3. Take quizzes for assessment
4. Receive personalized recommendations
5. Explore recommended career paths
6. Track progress on selected path

### Existing User Flow
1. Login to account
2. View dashboard
3. Take additional quizzes
4. Update profile information
5. View updated recommendations
6. Continue tracking career progress

## 🔄 Data Management

### Django Admin Features
- User management and editing
- Quiz question management
- Career path administration
- Career progress tracking
- Recommendation viewing
- Search and filtering capabilities

### Management Commands
```bash
# Seed career paths
python manage.py seed_careers

# Seed quiz questions
python manage.py seed_quizzes

# Create superuser
python manage.py createsuperuser

# Run migrations
python manage.py makemigrations
python manage.py migrate
```

## 📚 Included Sample Data

### 5 Career Paths
- Full Stack Developer
- Data Scientist
- Product Manager
- UI/UX Designer
- DevOps Engineer

### 5 Sample Quizzes
- Programming Skills Assessment
- Web Development Knowledge
- Interest in Technology
- Career Interest Assessment
- Learning Style Preference

## 🐛 Troubleshooting

### Port Already in Use
```bash
python manage.py runserver 8001
```

### Migration Issues
```bash
python manage.py migrate --fake-initial
```

### Static Files Not Loading
```bash
python manage.py collectstatic
```

### Database Issues
```bash
# Reset database (WARNING: deletes all data)
rm db.sqlite3
python manage.py migrate
python manage.py seed_careers
python manage.py seed_quizzes
```

## 📂 Project Structure

```
career-platform-django/
├── careerplatform/          # Project configuration
│   ├── settings.py
│   ├── urls.py
│   ├── views.py
│   └── wsgi.py
├── users/                   # User management
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
├── quizzes/                 # Quiz system
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── admin.py
│   └── management/
│       └── commands/
│           └── seed_quizzes.py
├── careers/                 # Career paths
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── admin.py
│   └── management/
│       └── commands/
│           └── seed_careers.py
├── recommendations/         # Recommendations
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
├── templates/               # HTML templates
│   ├── base.html
│   ├── index.html
│   ├── dashboard.html
│   ├── users/
│   ├── quizzes/
│   ├── careers/
│   └── recommendations/
├── static/                  # CSS and JavaScript
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── script.js
├── manage.py
├── db.sqlite3              # Database (auto-created)
└── venv/                   # Virtual environment
```

## 🚀 Production Deployment

For production use:

1. Set `DEBUG = False` in settings.py
2. Configure `ALLOWED_HOSTS`
3. Use PostgreSQL instead of SQLite
4. Set up environment variables
5. Use Gunicorn or uWSGI as WSGI server
6. Configure Nginx/Apache as reverse proxy
7. Set up SSL/TLS certificates
8. Enable security middleware

## 📝 License

This project is open source and available for educational and commercial use.

## 👨‍💻 Support

For issues or questions, please refer to the Django documentation:
- https://docs.djangoproject.com/
- https://www.djangoproject.com/

## 🎯 Future Enhancements

- [ ] Email notifications
- [ ] Advanced analytics dashboard
- [ ] Mentorship program
- [ ] Job board integration
- [ ] Social features (following, messaging)
- [ ] API endpoint documentation
- [ ] Mobile app version
- [ ] Machine learning recommendations
- [ ] Video tutorials integration
- [ ] Progress certification

---

**Platform Version**: 1.0.0
**Django Version**: 6.0.2
**Last Updated**: February 3, 2026
