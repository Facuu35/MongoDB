# Facundo Fernandez - Lab Report

## Date: 03/25/2024
## Lab Title: Node.js and Unit Testing – REST API in Node.js

### Summary
In these two labs, I worked with Node.js to create the structure of a web application. To begin with, I had to set up Node and install the dependencies. Then, I wrote 7 new methods with their headers and body. After this, I created 12 unit tests to test the functionality of my web application. Later, I created a RESTful API to handle all the requests to the server, including 4 basic CRUD operations using different HTTP verbs. Finally, I connected my Node.js app with a MongoDB server and used the Googleapis to set up authentication on my website. I then uploaded everything to my production environment to make this RESTful API public.

### Design Overview
To begin with, my project had the following folder structure:




Each of the files inside of models/ were my Mongoose Schemas. I had a Task.js and a User.js, Schemas are used to validate data that will be passed off to the server, in my case, to my MongoDB server, basically the Schemas hold the data that will be passed to the server. This is an example of my Task.js Schema:

![image](https://github.com/Facuu35/MongoDB/assets/17630462/676d7eca-5139-4132-9a62-69ccbe58ebaa)


Moreover, to authenticate, I used a Google API to simplify the sign-in process. I created an account in Google Cloud and retrieved my keys, secret ID, etc., to use it on my website.

### UML
[Insert UML diagram here]
Code extract from Task.js

I am defining UserId, Text, Done and Date. Those fields will be passed to the server.
Inside of my routes folder I had three files, auth.js, users.js and tasks.js, these are my endpoints, each of my endpoints has its own method handlers, to create, read, update and delete. My endpoints need to match their corresponding Schema objects.

This is an example of my tasks.js:
![image](https://github.com/Facuu35/MongoDB/assets/17630462/96f27d1a-79ec-48a6-9d7b-249f621faf74)
Code extract from tasks.js

Note how the task objects match the models Task.js (Mongoose Schema). At this point in my work, all I am intending to do is to display basic information on the web just to make sure everything is working as intended.
![image](https://github.com/Facuu35/MongoDB/assets/17630462/b27d3437-5292-4a20-9a78-de7d893a00fe)
This is an screenshot of the user endpoint printing only my user information.

![image](https://github.com/Facuu35/MongoDB/assets/17630462/eb377ff6-a623-439d-9d8c-57e0bab8ed0b)
This is an screenshot of the tasks enpoint printing only the tasks information.

Moreover, to authenticate I used a Google API to make the sign in process very simple, I created an account in Google Cloud and retrieved my keys, secret ID, etc. to use it in my website.

### Questions

#### LAB 4A

1. **Name and discuss at least two of the benefits of writing unit tests before writing code.**
   - **Verification of Code Functionality:** Writing unit tests allows verifying that the code performs as intended and passes the correct objects. This helps in identifying bugs early in the development process, making them easier to fix.
   - **Improved Documentation:** Unit tests serve as documentation for the application, providing insights into what the application should do. They help developers understand the expected behavior of the code.

2. **What would be some of the benefits of automating your test scripts (i.e., so they run at each commit)?**
   - **Time and Resource Savings:** Automating test scripts eliminates the need for manual intervention in the testing process, saving developers time and resources.
   - **Consistent Testing:** Automating tests to run at each commit ensures consistent testing, promoting a more efficient development workflow.

3. **How long did this lab take you?**
   - It took me around 5 hours.

#### LAB 4B

1. **List three advantages of using a web API.**
   - **Flexibility and Scalability:** APIs allow for integrating different systems, services, and applications, enabling the building of more flexible and scalable solutions.
   - **Modularity and Reusability:** APIs promote modularity and reusability by breaking down complex systems into smaller, manageable components.
   - **Improved User Experience:** APIs enhance the user experience by seamlessly integrating third-party services and data sources into applications.

2. **What are the differences between these four HTTP methods: GET, POST, PUT, and DELETE? Which ones are idempotent?**

   **GET:** This method is used to retrieve data from a specified resource. When a client sends a GET request, it requests data from the server without causing any modification to the resource. GET requests are typically used for fetching web pages, images, files, etc. It is a safe and idempotent method, meaning it does not modify the state of the server and can be repeated multiple times without changing the result.

   **POST:** POST requests are used to submit data to be processed to a specified resource. It is often used when submitting form data or uploading files to a server. Unlike GET requests, POST requests can cause modifications to the server's state, such as creating a new resource or updating existing data. POST requests are not idempotent because submitting the same data multiple times can result in the creation of multiple resources or different outcomes.

   **PUT:** PUT requests are used to update or replace existing data at a specified resource or create a new resource if it does not exist. It is similar to POST in that it can modify the server's state, but unlike POST, PUT requests are idempotent. This means that sending the same PUT request multiple times will have the same result, and it will not cause additional changes beyond the initial update.

   **DELETE:** DELETE requests are used to remove a specified resource from the server. When a client sends a DELETE request, it instructs the server to delete the resource identified by the request URL. Like PUT requests, DELETE requests are also idempotent. Sending the same DELETE request multiple times will have the same effect, removing the resource from the server each time.

   - **GET:** Retrieves data from a specified resource, safe and idempotent.
   - **POST:** Submits data to be processed to a specified resource, not idempotent.
   - **PUT:** Updates or replaces existing data at a specified resource, idempotent.
   - **DELETE:** Removes a specified resource from the server, idempotent.

### Lessons Learned
1. **Mismatch in Schema and Endpoint:** Ensure consistency between schemas and endpoints to avoid unexpected issues.
2. **Middleware Setup:** Understand the importance of middleware setup for proper functioning of the application, such as Passport.js for authentication and session management.
3. **Unit Testing:** Properly understand and implement unit tests, ensuring compatibility with endpoint routes and handling of errors.

### Conclusion
- Developed a RESTful API with Mongoose schemas and endpoints in the web application.
- Implemented Googleapis for user authentication.
- Created unit tests to test endpoint routes.
- Successfully moved development code to production environment.
