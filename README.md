# Rails Generate Resource / Postman

- API (Application Programming Interface): responsible for transmitting info across the internet as JSON

- JSON (Javascript Object Notation): data structure supported by most programming languages

## Rails Generate Resource
`$ rails g resource Student name:string cohort:string`
- Migration file
- Model + Spec file
- Controller + Spec file
- Views (which we removed)
- Helpers
- Resource Routes: This gives us all of our restful routes!


## RESTful Routes
- Index - Gets all the instances for that model
- Show - Gets one instance
- New - Form
- Create - Adds an instance to that database
- Edit - Form
- Update - Patches or Puts the database
- Destroy - Deletes an instance

Only RESTful Routes needed for API:
- Index
- Show
- Create
- Update
- Destroy

## Postman
Postman is a GUI for API's

- file > new > HTTP Request
- run rails server `$ rails s`

### Index
- We wrote our index method in our controller
- Set a GET request in postman to url: localhost:3000/students

### Show
- Wrote our show method to include params
- Set a GET request in postman to url: localhost:3000/students/2 (2 is the id of the student)

### Create
- Wrote our create method, checking if the student is valid after running through strong params.
- Set a POST request in postman to url: localhost:3000/students, however we passed params in postman
    - Body > Raw > Text -> JSON

### Update
- Wrote our update method, by first pulling param from url, passing strong params and if valid rendered json
- Set a PATCH request in postman to url: localhost:3000/students/6, and also added in the params in postman of content to be edited

### Destroy
- Wrote our destroy method, by first pulling params from url, then checking that it was a success and the render json
- Set a DELETE request in postman to url: localhost:3000/students/1

# Troubleshooting
- In Postman: if seeing html in our view, click on preview to see rails error
- Check your server if all else fails and trace the request response cycle