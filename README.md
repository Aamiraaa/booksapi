# booksapi
#Create a Python virtual environment and activate it
python3 -m venv venv
source venv/bin/activate

#Install the required dependencies
pip install -r requirements.txt

#Apply database migrations
python manage.py makemigrations
python manage.py migrate

#Start the development server
python manage.py runserver

The API will be accessible at http://localhost:8000/.

API Endpoints
Authentication
POST /api/token/: Obtain a JWT token by providing your username and password.
Book Operations
GET /api/books/: List all books.
GET /api/books/<id>/: Retrieve a specific book by ID.
POST /api/books/: Create a new book.
PUT /api/books/<id>/: Update an existing book.
DELETE /api/books/<id>/: Delete a book.

Example API Requests
Obtain a JWT Token
curl -X POST http://localhost:8000/api/token/ -d "username=yourusername&password=yourpassword"

#List All Books
curl -H "Authorization: Bearer YOUR_ACCESS_TOKEN" http://localhost:8000/api/books/

#Retrieve a Specific Book
curl -H "Authorization: Bearer YOUR_ACCESS_TOKEN" http://localhost:8000/api/books/<id>/

#Create a New Book
curl -X POST -H "Authorization: Bearer YOUR_ACCESS_TOKEN" http://localhost:8000/api/books/ -d "title=New Book&author=Author&published_date=2023-11-03&isbn=1234567890123"

#Update an Existing Book
curl -X PUT -H "Authorization: Bearer YOUR_ACCESS_TOKEN" http://localhost:8000/api/books/<id>/ -d "title=Updated Book&author=New Author&published_date=2023-11-03&isbn=9876543210987"

#Delete a Book
curl -X DELETE -H "Authorization: Bearer YOUR_ACCESS_TOKEN" http://localhost:8000/api/books/<id>/


Make sure to replace placeholders such as `yourusername`, `yourpassword`, and `YOUR_ACCESS_TOKEN` with your actual credentials and tokens. This README provides clear instructions on how to set up the project and how to use the API, including authentication and example API requests using `curl`.
