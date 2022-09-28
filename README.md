# My First App by Name "Trivia" to document 


This is a trivia app that is an assignment by udacity through the ALX program. The idea behind the app is to create a bond between the students and employees at Udacity. The application must 
1. Display questions - both all questions and by category. Questions should show the question, category and difficulty rating by default and can show/hide the answer.
2. Delete questions.
3. Add questions and require that they include question and answer text.
4. Search for questions based on a text query string.
5. Play the quiz game, randomizing either all questions or within a specific category.

By completing this project it was enough justification that I have learned and I am able to apply skills and implemment well formatted API endpoints that leverage knowledge of HTTP and API develoment practices

# General Guidelines
This project contains TODOs that I have completed as part of the asssignment for completion of Full stack developer nanodegree course. The frontend section forms aslo contains the TODOs part that I had to complete in order to form with a complete reference in order to match the endpoints and programmed behaviour.

## Getting started 
### Pre-requisities and Local Deevelopment

Developers using this project should already have python3, pip and node installed on their local machines.

#### Backend
From the backend folder run 'pip install requirements.txt'. all required packages are included in the requirements file

To run the application rexcute the following commnads

'''
export FLASKR_APP=flaskr
flask run --reload
'''
These commands put the applicAtion in ndevelopment and directs our application to use '__init__.py' file in our flaskr folder. Working in development mode shows an interactive debuuger in console and restarts the server whenever changes are made. If running locally in windwows look for commands in [Flask documentation](http://flask.pocoo.org/docs/1.0/tutorial/factory/).

This application is running on 'http://127.0.0.1:5000/' by default and is a proxy in the frondend configuration.

### Frondend
From the frondend folder, run the following commands to start the client:

'''
npm install // only once to install dependencies
npm start
''

By default the frondend wil run on localhost:3000.


### Tests

In order to run tests navigate to the backend folder and run the following commands:

'''
dropdb trivia_test
createdb trivia_test
psql trivia_test < trivia.psql
python test_flaksr.py

'''

The first time you run the tests, omit the drop db command

All testt are kept in that file and should be mantained as updates are to the app functionality.

### API Reference

### Getting Starteed

- base URL: At present this app can only run locally and is not hosted as a base URL. The backend app is hosted at default, 'http://127.0.0.1:5000/', which is set as proxy in the frondend configuration.
- Authentication: This version of the application does not require authentication or API  Keys


### Error Handling

Errors are returned as JSON obbjects in the following formart:

''' {
    "success": False,
    "error":400,
    "message":"bad request"
    }
'''

THe API will return three errors when the request fails
- 400: Bad Request
- 404: resource not found
- 422: unprocessable

### Endpoints

#### Get /Questions

- General:
    - Returns a list of questions objects, success value and total number of questions
    - Results are paginated in groups of 10 . Include a argument to choose a page number, starting from 1
- Sample: 'curl http://127.0.0.1:5000/questions'


''' {
    "Questions": [
        {
            "answer": "Apollo 13",
            "category": "5",
            "difficulty": 4,
            "id": 2,
            "question": "What movie earned Tom Hanks his third straight Oscar nomination, in 1996?"
        },
        {
            "answer": "Tom Cruise",
            "category": "5",
            "difficulty": 4,
            "id": 4,
            "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
        },
        {
            "answer": "Edward Scissorhands",
            "category": "5",
            "difficulty": 3,
            "id": 6,
            "question": "What was the title of the 1990 fantasy directed by Tim Burton about a young man with multi-bladed appendages?"
        },
        {
            "answer": "Brazil",
            "category": "6",
            "difficulty": 3,
            "id": 10,
            "question": "Which is the only team to play in every soccer World Cup tournament?"
        },
        {
            "answer": "Uruguay",
            "category": "6",
            "difficulty": 4,
            "id": 11,
            "question": "Which country won the first ever soccer World Cup in 1930?"
        },
        {
            "answer": "George Washington Carver",
            "category": "4",
            "difficulty": 2,
            "id": 12,
            "question": "Who invented Peanut Butter?"
        },
        {
            "answer": "Lake Victoria",
            "category": "3",
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
        },
        {
            "answer": "Agra",
            "category": "3",
            "difficulty": 2,
            "id": 15,
            "question": "The Taj Mahal is located in which Indian city?"
        },
        {
            "answer": "Escher",
            "category": "2",
            "difficulty": 1,
            "id": 16,
            "question": "Which Dutch graphic artist–initials M C was a creator of optical illusions?"
        },
        {
            "answer": "Mona Lisa",
            "category": "2",
            "difficulty": 3,
            "id": 17,
            "question": "La Giaconda is better known as what?"
        }
    ],
    "success": true,
    "total_questions": 12
}

'''



#### GET /categories
- General:
    - Returns a list of categories objects, success value, and total number of categories
- Sample: 'curl http://127.0.0.1:5000/categories'
''' {
    "list_categories": [
        {
            "id": 1,
            "type": "Science"
        },
        {
            "id": 2,
            "type": "Art"
        },
        {
            "id": 3,
            "type": "Geography"
        },
        {
            "id": 4,
            "type": "History"
        },
        {
            "id": 5,
            "type": "Entertainment"
        },
        {
            "id": 6,
            "type": "Sports"
        }
    ],
    "success": true,
    "total_categories": 6
}
'''{
    "deleted": 4,
    "questions": [
        {
            "answer": "Edward Scissorhands",
            "category": "5",
            "difficulty": 3,
            "id": 6,
            "question": "What was the title of the 1990 fantasy directed by Tim Burton about a young man with multi-bladed appendages?"
        },
        {
            "answer": "Brazil",
            "category": "6",
            "difficulty": 3,
            "id": 10,
            "question": "Which is the only team to play in every soccer World Cup tournament?"
        },
        {
            "answer": "Uruguay",
            "category": "6",
            "difficulty": 4,
            "id": 11,
            "question": "Which country won the first ever soccer World Cup in 1930?"
        },
        {
            "answer": "George Washington Carver",
            "category": "4",
            "difficulty": 2,
            "id": 12,
            "question": "Who invented Peanut Butter?"
        },
        {
            "answer": "Lake Victoria",
            "category": "3",
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
        },
        {
            "answer": "Agra",
            "category": "3",
            "difficulty": 2,
            "id": 15,
            "question": "The Taj Mahal is located in which Indian city?"
        },
        {
            "answer": "Escher",
            "category": "2",
            "difficulty": 1,
            "id": 16,
            "question": "Which Dutch graphic artist–initials M C was a creator of optical illusions?"
        },
        {
            "answer": "Mona Lisa",
            "category": "2",
            "difficulty": 3,
            "id": 17,
            "question": "La Giaconda is better known as what?"
        },
        {
            "answer": "One",
            "category": "2",
            "difficulty": 4,
            "id": 18,
            "question": "How many paintings did Van Gogh sell in his lifetime?"
        },
        {
            "answer": "Jackson Pollock",
            "category": "2",
            "difficulty": 2,
            "id": 19,
            "question": "Which American artist was a pioneer of Abstract Expressionism, and a leading exponent of action painting?"
        }
    ],
    "success": true,
    "total_questions": 10
}
#### POST/questions
- General:
    - Returns a list of categories objects
    - creates a new question using the submitted question, answer, category and difficulty. Returns the id of created question, success value, total questions, and question list based on the current number to update the frontend
    - `curl -X POST -H "Content-Type: application/json" -d '{"question":"where is kenya", "answer":"africa", "category":"1", "difficulty":"1"}' http://127.0.0.1:5000/questions'

'''
{
    "message":"Question created successfully",
    "success":true
}
#### DELETE/questions/{question_id}
- General:
    - Deletes the question of the given ID if it exists. Returns the id of deleted question, success value, total questions, and book list based on the current page to update the front end
- 'curl -X DELETE http://127.0.0.1:5000/questions/2?page=1'

'''
{
    "deleted": 4,
    "questions": [
        {
            "answer": "Edward Scissorhands",
            "category": "5",
            "difficulty": 3,
            "id": 6,
            "question": "What was the title of the 1990 fantasy directed by Tim Burton about a young man with multi-bladed appendages?"
        },
        {
            "answer": "Brazil",
            "category": "6",
            "difficulty": 3,
            "id": 10,
            "question": "Which is the only team to play in every soccer World Cup tournament?"
        },
        {
            "answer": "Uruguay",
            "category": "6",
            "difficulty": 4,
            "id": 11,
            "question": "Which country won the first ever soccer World Cup in 1930?"
        },
        {
            "answer": "George Washington Carver",
            "category": "4",
            "difficulty": 2,
            "id": 12,
            "question": "Who invented Peanut Butter?"
        },
        {
            "answer": "Lake Victoria",
            "category": "3",
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
        },
        {
            "answer": "Agra",
            "category": "3",
            "difficulty": 2,
            "id": 15,
            "question": "The Taj Mahal is located in which Indian city?"
        },
        {
            "answer": "Escher",
            "category": "2",
            "difficulty": 1,
            "id": 16,
            "question": "Which Dutch graphic artist–initials M C was a creator of optical illusions?"
        },
        {
            "answer": "Mona Lisa",
            "category": "2",
            "difficulty": 3,
            "id": 17,
            "question": "La Giaconda is better known as what?"
        },
        {
            "answer": "One",
            "category": "2",
            "difficulty": 4,
            "id": 18,
            "question": "How many paintings did Van Gogh sell in his lifetime?"
        },
        {
            "answer": "Jackson Pollock",
            "category": "2",
            "difficulty": 2,
            "id": 19,
            "question": "Which American artist was a pioneer of Abstract Expressionism, and a leading exponent of action painting?"
        }
    ],
    "success": true,
    "total_questions": 10
}
'''


## Deployment N/A

## Authors
Yours Truly, Vincent Kimilu

## Acknowledgements
The awesome team from udacicty and all my mentors from ALX. Thanks You All