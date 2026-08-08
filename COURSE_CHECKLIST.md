# Coursera Peer-Grade Checklist

Use this checklist before resubmitting the Little Lemon Web Application.

## Starting the project
- [x] Django project structure
- [x] Git-friendly repository structure
- [x] Static/template-driven Django pages
- [x] `manage.py`
- [x] `requirements.txt`

## Project functionality
- [x] MySQL database configuration
- [x] `Menu` model
- [x] `Booking` model
- [x] Django REST Framework
- [x] Menu API CRUD
- [x] Table booking API CRUD
- [x] Django admin

## Security and testing
- [x] User registration through Djoser
- [x] Token login/logout
- [x] Secured table booking API
- [x] Unit tests
- [x] Insomnia testing instructions

## Before submitting
1. Configure MySQL or use SQLite only for local smoke testing.
2. Run `python manage.py migrate`.
3. Run `python manage.py test`.
4. Run `python manage.py runserver`.
5. Test the API in Insomnia.
6. Take screenshots showing successful API requests/responses if Coursera asks for evidence.
7. Push the complete project structure to GitHub.
8. Never commit real passwords, tokens, or `.env` files.

The implementation is designed to cover the course outcomes listed on the Coursera
Back-End Developer Capstone page. Peer graders still evaluate the submitted
repository and evidence, so run the project and verify the endpoints before
resubmitting.
