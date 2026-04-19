# Quick Start Guide - Django Career Platform

## ⚡ Get Running in 2 Minutes

### 1. Open PowerShell and Navigate to Project

```powershell
cd "C:\Users\manis\OneDrive\Desktop\Majorproject\career-platform-django"
```

### 2. Activate Virtual Environment

```powershell
& ".\venv\Scripts\Activate.ps1"
```

### 3. Start the Server

```powershell
python manage.py runserver
```

### 4. Open Browser

Navigate to: **http://localhost:8000**

## 🔑 Default Login Credentials

```
Username: admin
Password: admin123
Email: admin@example.com
```

## 📖 What's Included

✅ **User Authentication** - Registration, login, profile management
✅ **5 Career Paths** - Full Stack Dev, Data Scientist, Product Manager, Designer, DevOps
✅ **5 Sample Quizzes** - Skills, interests, and learning style assessments
✅ **Recommendations Engine** - Smart matching based on user profile
✅ **Admin Dashboard** - Full Django admin at http://localhost:8000/admin
✅ **Responsive Design** - Works on desktop, tablet, and mobile

## 🗺️ Main Routes

| URL | Purpose |
|-----|---------|
| `/` | Home page |
| `/dashboard/` | User dashboard |
| `/auth/register/` | Register new account |
| `/auth/login/` | Login to account |
| `/auth/profile/` | Edit user profile |
| `/quizzes/` | Take quizzes |
| `/careers/` | Browse career paths |
| `/recommendations/` | View personalized recommendations |
| `/admin/` | Django admin panel |

## 🎯 Try This Flow

1. Go to http://localhost:8000
2. Click "Register" and create new account
3. Go to "Update Profile" and add your skills and interests
4. Take some quizzes in "Quizzes"
5. Go to "Recommendations" to see your matches
6. Click any career to see details and roadmap

## 🛑 Stop the Server

Press `CTRL + C` in the terminal

## 🔧 Useful Commands

```powershell
# Start server on different port
python manage.py runserver 8001

# Create new admin user
python manage.py createsuperuser

# Reset all data (WARNING: destructive!)
rm db.sqlite3
python manage.py migrate
python manage.py seed_careers
python manage.py seed_quizzes

# View database
python manage.py dbshell
```

## 📚 Tech Stack

- **Backend**: Django 6.0.2
- **Database**: SQLite3
- **Frontend**: HTML + CSS + JavaScript
- **Templates**: Jinja2
- **Authentication**: Django Sessions

## 🎨 Features at a Glance

### Quiz Center
- 5 different quiz types
- Categories: Skills, Interests, Learning Style
- Question types: Multiple Choice, Rating, Text
- Score tracking

### Career Paths
- 5 detailed career paths
- 3-phase roadmaps (Foundation → Intermediate → Advanced)
- Salary ranges and job outlook
- Required skills and education
- Company examples
- Learning resources

### Recommendations
- Personalized matching algorithm
- Score breakdown (Skills 40%, Interests 40%, Experience 20%)
- Ranked by match percentage
- Color-coded visual indicators

## 🚀 Next Steps

1. Explore all features on the platform
2. Try the Django admin at `/admin/`
3. Review the models in Django shell
4. Customize colors/styling in `/static/css/style.css`
5. Add more quiz questions or careers via admin

## 📞 Need Help?

All features and setup instructions are in the full README.md file.
