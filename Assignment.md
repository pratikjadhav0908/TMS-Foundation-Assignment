# ✅ Task 2: Technical Proficiency

## 2(a) Handling CORS in Django + React

###  Problem
API Integration: In a Django + React setup, how would you handle Cross-Origin Resource Sharing (CORS) issues?



#### {1️} Install Required Package

pip install django-cors-headers


#### {2} Add to `INSTALLED_APPS`

INSTALLED_APPS = [
    'corsheaders',
    ...
]


#### {3} Configure Middleware (Order Is Important)

MIDDLEWARE = [
    'corsheaders.middleware.CorsMiddleware',
    'django.middleware.common.CommonMiddleware',
]


#### {4} Allow Trusted Frontend Origins

CORS_ALLOWED_ORIGINS = [
    "http://localhost:3000",
    "https://dev.bharatyuva.org"
]


#### {5} Enable Credentials for Authentication APIs

CORS_ALLOW_CREDENTIALS = True




## 📌 2(c) Handling Migration Conflicts in Django (Team Environment)

### Problem
Database Management: How do you handle a "Migration Conflict" in Django when multiple developers are working on the same database schema?


#### {1} Pull the Latest Code

git pull origin main


#### {2} Review Existing Migrations

python manage.py showmigrations


#### {3} Resolve Conflicts
- Remove only conflicting **local** migration files  
- Recreate clean migrations:

python manage.py makemigrations


#### {4} Apply Migrations Carefully

python manage.py migrate




### 📘 Golden Rules for Team Collaboration
- Only one developer should merge database schema changes at a time  
- Follow clear and consistent migration naming conventions  
- Communicate model changes within the team before pushing  



### ✅ Result
Following this approach prevents data corruption, reduces migration conflicts, and ensures smooth deployments in collaborative Django projects.
