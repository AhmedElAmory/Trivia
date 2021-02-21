# Full Stack Trivia API Backend

## Getting Started

### Installing Dependencies

#### Python 3

Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)

#### Virtual Enviornment

I recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organaized. 
Instructions for setting up a virual enviornment:

```
python -m virtualenv env
source env/bin/activate
```

For Windows users:

```
python -m virtualenv env
env\Scripts\activate
```

#### PIP Dependencies

Once you have your virtual environment setup and running, install dependencies by naviging to the `/backend` directory and running:

```
pip install -r requirements.txt
```

This will install all of the required packages selected within the `requirements.txt` file.

##### Key Dependencies

- [Flask](http://flask.pocoo.org/)  is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) is the Python SQL toolkit and ORM I used to handle the lightweight sqlite database.

- [Flask-CORS](https://flask-cors.readthedocs.io/en/latest/#) is the extension I used to handle cross origin requests from my frontend server. 

## Database Setup

1. Create an empty postgres database called trivia 

2. With Postgres running, restore a database using the trivia.psql file provided. From the backend folder in terminal run:
```
psql trivia < trivia.psql
```

## Running the server

From within the `backend` directory first ensure you are working using your created virtual environment.

To run the server, execute:

```
export FLASK_APP=flaskr
export FLASK_ENV=development
flask run
```

For windows users :

```
set FLASK_APP=flaskr
set FLASK_ENV=development
flask run
```

Setting the `FLASK_ENV` variable to `development` will detect file changes and restart the server automatically.

Setting the `FLASK_APP` variable to `flaskr` directs flask to use the `flaskr` directory and the `__init__.py` file to find the application. 

## API Documentation
## End Points

### GET /questions

returns a list of the available questions

response sample:
```
{
  "categories": [
    "Science",
    "Art",
    "Geography",
    "History",
    "Entertainment",
    "Sports"
  ],
  "success": true
}
```
### DELETE /question/\<int:question_id\>

deletes a certain question using its ID

response sample:
```
{
  "success": true
}
```
POST /question

add a new question

response sample:
```
{
  "success": true
}
```
### POST /questions/search

searches for the available questions containing a certain string

response sample:
```
{
"success": true,
"questions": [
  {
  "id": 22, 
  "question": "Hematology is a branch of medicine involving the study of what?",
  "answer": 'Blood',
  "category": 1,
  "difficulty": 4
  }
],
"total_questions": 1,
"currentCategory": "Science"
}
```
### GET /category/\<int:id\>/questions

returns a list of questions of a specific category

response sample:
```
{
  "current_category": "Art",
  "questions": [
    {
      "answer": "Escher",
      "category": 2,
      "difficulty": 1,
      "id": 16,
      "question": "Which Dutch graphic artist\u2013initials M C was a creator of optical illusions?"
    },
    {
      "answer": "Mona Lisa",
      "category": 2,
      "difficulty": 3,
      "id": 17,
      "question": "La Giaconda is better known as what?"
    },
    {
      "answer": "One",
      "category": 2,
      "difficulty": 4,
      "id": 18,
      "question": "How many paintings did 
Van Gogh sell in his lifetime?"
    },
    {
      "answer": "Jackson Pollock",        
      "category": 2,
      "difficulty": 2,
      "id": 19,
      "question": "Which American artist was a pioneer of Abstract Expressionism, and a leading exponent of action painting?" 
    },
    {
      "answer": "",
      "category": 2,
      "difficulty": 1,
      "id": 36,
      "question": "pol"
    },
    {
      "answer": "",
      "category": 2,
      "difficulty": 1,
      "id": 42,
      "question": "ok"
    },
    {
      "answer": "za",
      "category": 2,
      "difficulty": 1,
      "id": 61,
      "question": "za"
    }
  ],
  "success": true,
  "total_questions": 7
}
```
### POST /quizzes

start a quiz of a specific category

response sample:
```
{
  "success":true,
  "question":{
                "answer": "Escher",
                "category": 2,
                "difficulty": 1,
                "id": 16,
                "question": "Which Dutch graphic artist\u2013initials M C was a creator of optical illusions?"
             }
}
```

## Testing
To run the tests, run
```
dropdb trivia_test
createdb trivia_test
psql trivia_test < trivia.psql
python test_flaskr.py
```
