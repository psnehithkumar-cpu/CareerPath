# Installation & Setup Guide

## System Requirements

- Windows 10/11, macOS, or Linux
- Python 3.8 or higher
- pip (Python package manager)
- 100MB free disk space

## Step-by-Step Installation

### 1. Open Terminal/PowerShell

**Windows**: Press `Win + R`, type `powershell`, press Enter

### 2. Navigate to Project Directory

```powershell
cd "C:\Users\manis\OneDrive\Desktop\Majorproject\career-platform-django"
```

### 3. Create Virtual Environment

```powershell
python -m venv venv
```

This creates an isolated Python environment for the project.

### 4. Activate Virtual Environment

```powershell
& ".\venv\Scripts\Activate.ps1"
```

You should see `(venv)` at the start of your terminal prompt.

### 5. Install Dependencies

```powershell
pip install -r requirements.txt
```

This installs Django and other required packages.

Alternatively, install manually:
```powershell
pip install Django==6.0.2 djangorestframework==3.16.1 django-cors-headers==4.9.0 python-dotenv==1.2.1 Pillow==12.1.0
```

### 6. Create Database & Run Migrations

```powershell
python manage.py migrate
```

This creates the SQLite database and tables.

### 7. Create Admin User (Optional)

```powershell
python manage.py createsuperuser
```

Enter username, email, and password when prompted.

Or use default: `admin` / `admin123`

### 8. Seed Sample Data

```powershell
python manage.py seed_careers
python manage.py seed_quizzes
```

This populates the database with sample careers and quizzes.

### 9. Start Development Server

```powershell
python manage.py runserver
```

You should see:
```
Starting development server at http://127.0.0.1:8000/
```

### 10. Open in Browser

Navigate to: **http://localhost:8000**

## 🎉 You're Done!

The Career Platform is now running!

## First Steps

1. **Go Home**: http://localhost:8000/
2. **Register**: Create a new account
3. **Complete Profile**: Add your skills and interests
4. **Take Quizzes**: Complete some assessments
5. **Get Recommendations**: View personalized career matches
6. **Explore Careers**: Click on recommended careers to see roadmaps

## Admin Panel

Access Django admin at: http://localhost:8000/admin

Default credentials:
- Username: `admin`
- Password: `admin123`

Here you can:
- Manage users
- Add/edit quizzes
- Add/edit career paths
- View recommendations
- Track quiz attempts

## Troubleshooting

### Virtual Environment Issues

**Problem**: `Activate.ps1 cannot be loaded`

**Solution**: Run PowerShell as Administrator:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
& ".\venv\Scripts\Activate.ps1"
```

### Port Already in Use

**Problem**: Port 8000 is already in use

**Solution**: Use a different port:
```powershell
python manage.py runserver 8001
```

### Database Issues

**Problem**: "No such table" error

**Solution**: Reset the database:
```powershell
rm db.sqlite3
python manage.py migrate
python manage.py seed_careers
python manage.py seed_quizzes
```

### Missing Dependencies

**Problem**: Module not found error

**Solution**: Reinstall dependencies:
```powershell
pip install -r requirements.txt --upgrade
```

## Project Structure After Installation

```
career-platform-django/
├── venv/                          # Virtual environment (auto-created)
├── careerplatform/
├── users/
├── quizzes/
├── careers/
├── recommendations/
├── templates/
├── static/
├── db.sqlite3                     # Database (auto-created)
├── manage.py
├── README.md
├── QUICKSTART.md
├── PROJECT_SUMMARY.md
└── requirements.txt
```

## Common Commands Reference

```powershell
# Activate virtual environment
& ".\venv\Scripts\Activate.ps1"

# Deactivate virtual environment
deactivate

# Run migrations
python manage.py migrate

# Create migrations
python manage.py makemigrations

# Start server
python manage.py runserver

# Create superuser
python manage.py createsuperuser

# Access Django shell
python manage.py shell

# Seed careers
python manage.py seed_careers

# Seed quizzes
python manage.py seed_quizzes

# Collect static files
python manage.py collectstatic

# Check for issues
python manage.py check
```

## Database Management

The project uses SQLite by default. The database file is `db.sqlite3`.

### Backup Database
```powershell
Copy-Item db.sqlite3 db.sqlite3.backup
```

### Reset Database
```powershell
rm db.sqlite3
python manage.py migrate
python manage.py seed_careers
python manage.py seed_quizzes
```

## Python Version Check

Verify you have Python 3.8+:
```powershell
python --version
```

Should output something like: `Python 3.10.0`

## Next Steps

1. Explore all platform features
2. Read the full README.md for complete documentation
3. Customize styling in `static/css/style.css`
4. Add more quiz questions via Django admin
5. Add more career paths via Django admin

## Getting Help

- Django Documentation: https://docs.djangoproject.com/
- Django Official Site: https://www.djangoproject.com/
- Python Documentation: https://docs.python.org/3/

## Success Indicators

✅ Virtual environment created
✅ Dependencies installed
✅ Database created
✅ Sample data loaded
✅ Server running at http://localhost:8000
✅ Admin accessible at http://localhost:8000/admin

Congratulations! Your Career Platform is ready to use! 🚀
