# Brief Report
## 1. Design Choices
- Service Layer: I used a service layer (BookService.java) to separate business logic from the controller.
- I also used lombok to reduce boilercode.
- RESTful API: The BookController.java provides a REST API with proper usage of HTTP methods (GET, POST, PUT, DELETE). The mappings use path variables for id and request bodies to transfer data.
## 2. Challenges and Solutions
- SQLite Integration: One challenge was integrating SQLite with Spring Boot, which required some research into the proper configuration of the application.properties file and adding the correct dialect for Hibernate to understand SQLite queries. Using the SQLiteDialect in application.properties helped resolve this.
- Testing the API: Initially, I faced issues with POST requests in Postman not being accepted due to incorrect JSON formatting. I overcame this by ensuring that the Book class was correctly mapped to the JSON structure being sent via the request body.
## 3. Sample Requests and Responses
- Add a Book (POST Request)
- URL: POST http://localhost:8080/api/books

### Request Body:
```
{
  "title": "To Kill a Mockingbird",
  "author": "Harper Lee",
  "publicationYear": 1960
}
```
### Response:

```
{
  "id": 1,
  "title": "To Kill a Mockingbird",
  "author": "Harper Lee",
  "publicationYear": 1960
}
```
- Get All Books (GET Request)
- URL: GET http://localhost:8080/api/books

### Response:

```
[
  {
    "id": 1,
    "title": "To Kill a Mockingbird",
    "author": "Harper Lee",
    "publicationYear": 1960
  }
]
```
- Update a Book (PUT Request)
- URL: PUT http://localhost:8080/api/books/1

### Request Body:

```
{
  "title": "To Kill a Mockingbird",
  "author": "Harper Lee",
  "publicationYear": 1961
}
```
### Response:

```
{
  "id": 1,
  "title": "To Kill a Mockingbird",
  "author": "Harper Lee",
  "publicationYear": 1961
}
```
- Delete a Book (DELETE Request)
- URL: DELETE http://localhost:8080/api/books/1

### Response:

```
{
  "status": "OK"
}
```