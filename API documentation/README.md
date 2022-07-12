# Udacity Bookshelf APP

Welcome to the Udacity Bookshelf app. This app allows you to get books that are uploaded on a bookshelf virtually. This project was created from the udacity fullstack development track. This is the second project from the full stack development track which teaches all to know about RESTFUl APIs. This project also appreciate contributions from developerss who would like to make this project to have better user experience. The backend of this project is powered by Flask and the frontend is powered by React. All backend code follows [PEP8 style guidelines](https://www.python.org/dev/peps/pep-0008/). 


## Getting Started

### Pre-requisites and Dependencies
To run this basic app, you should already have python3, pip3 and node installed on your local machine.

#### Backend


in the backend folder, run `pip install -r requirements.txt`, in other to install all the required packages to run the app.


##OR

You call also run 
```
call .env/Scripts/activate on windows.
source .env/Scripts/activate  on mac.
```

Note the above command is not necessary but will be if you don't want to install the required packages on your local machin. This is for the backend.

To run the application run the following commands: 

    ###On windows:
```
        set FLASK_APP=flaskr
        set FLASK_ENV=development
        flask run
```
        
    ###On mac/linux:
```
        export FLASK_APP=flask
        export FLASK_ENV=development
        flask run
```

The following commands will make the flask to run from the flaskr directory and run all the codes from the __init__.py file.

After the app has started running successfully, copy the localhost link http://127.0.0.1:5000 or http://localhost:5000. The server is now running on th port 5000.

#### Frontend

Navigate to the frontend folder and run the following command:
```
    npm install
    npm start
```
the following command will install the required dependencies and run the app on localhost:3000.
 

### Tests

In order to run tests, In the backend folder, run tthe following command:
```
    dropdb bookshelf_test
    createdb bookshelf_test
    psql bookshelf_test < books.psql
    python test.py
```
All tests are kept in the test file  



## API Reference

### Getting Started

- Base URL: This api cannot be accessed online. It can only be accessed locally by running it from the localhost @ http://127.0.0.1:5000 after running the backend which runs the whole frontend
- Authentication: This app version does not support authentication.


### Error Handling
This app returns only one of the following errors:

- 404:"Resource not found"
- 400: "Bad request"
- 422: "Unprocessable"

Error is returned in the JSON format as seen below
```
{
    "success": False, 
    "error": 400,
    "message": "bad request"
}


### Endpoint Library

#### GET /books
Returns All the books Which will be paginated in a group of 8 books per page. 1. 

- Sample:
`curl http://127.0.0.1:5000/books`

- Returns:
``` {
  "books": [
    {
      "author": "Stephen King",
      "id": 1,
      "rating": 5,
      "title": "The Outsider: A Novel"
    },
    {
      "author": "Lisa Halliday",
      "id": 2,
      "rating": 5,
      "title": "Asymmetry: A Novel"
    },
    {
      "author": "Kristin Hannah",
      "id": 3,
      "rating": 5,
      "title": "The Great Alone"
    },
    {
      "author": "Tara Westover",
      "id": 4,
      "rating": 5,
      "title": "Educated: A Memoir"
    },
    {
      "author": "Jojo Moyes",
      "id": 5,
      "rating": 5,
      "title": "Still Me: A Novel"
    },
    {
      "author": "Leila Slimani",
      "id": 6,
      "rating": 5,
      "title": "Lullaby"
    },
    {
      "author": "Amitava Kumar",
      "id": 7,
      "rating": 5,
      "title": "Immigrant, Montana"
    },
    {
      "author": "Madeline Miller",
      "id": 8,
      "rating": 5,
      "title": "CIRCE"
    }
  ],
"success": true,
"total_books": 18
}
```


#### POST /books
Create a new book using  the curl link followed by the data to be created to the database:

- Sample:
`curl -X POST http://127.0.0.1:5000/books "Content-Type: application/json" -d {title:" Everything Sucks", author: 'Vaultboy', rating: 4}`

- Returns:
```
{
    books[
        {
            id: '34',
            title:" Everything sucks", 
            author: "Vaultboy", 
            rating: 4
        }
    ],
    "created book": 34,
    "success": True,
    "total_books": 19
}
```


#### DELETE /books/{book_id}
Delete a book from the bookshelf based on the book_id given in the enpoint URL.

- Sample:
`curl -X DELETE http://127.0.0.1:5000/books/22?page=4`

- Returns:
```
{
"books": [
    {
      "author": "Stephen King",
      "id": 1,
      "rating": 5,
      "title": "The Outsider: A Novel"
    },
    {
      "author": "Lisa Halliday",
      "id": 2,
      "rating": 5,
      "title": "Asymmetry: A Novel"
    },
    {
      "author": "Kristin Hannah",
      "id": 3,
      "rating": 5,
      "title": "The Great Alone"
    },
    {
      "author": "Tara Westover",
      "id": 4,
      "rating": 5,
      "title": "Educated: A Memoir"
    },
    {
      "author": "Jojo Moyes",
      "id": 5,
      "rating": 5,
      "title": "Still Me: A Novel"
    },
    {
      "author": "Leila Slimani",
      "id": 6,
      "rating": 5,
      "title": "Lullaby"
    },
    {
      "author": "Amitava Kumar",
      "id": 7,
      "rating": 5,
      "title": "Immigrant, Montana"
    },
    {
      "author": "Madeline Miller",
      "id": 8,
      "rating": 5,
      "title": "CIRCE"
    }
  ],
"success": "deleted",
"deleted book": 22,
"total_books": 18,
}
```


#### PATCH /books/{book_id}
Change the rating of a current book of the author. selected from the {book_id}.

- Sample:
- `curl -X PATCH http://127.0.0.1:5000/books/34 "Content-Type: application/json" -d {rating: 3}"`

- Returns:
```
{
books: [
    id: '34',
    title: "Everything Sucks", 
    author: "Vaultboy", 
    rating: 3
],
"id": 34
"success": True,
}
```



## Deployment N/A



##Authors

This web app was fully completed myself Shina-Kelani Taiwo.



## Acknowledgements 

Thanks to the Udacity instructor on full stack development lesson 2. And to Udacity and all its instructors. Hippy!

