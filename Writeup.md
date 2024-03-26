# Facundo Fernandez - Lab Report

## Date: 03/25/2024
## Lab Title: Node.js and Unit Testing – REST API in Node.js

### Summary
In these two labs, I worked with Node.js to create the structure of a web application. To begin with, I had to set up Node and install the dependencies. Then, I wrote 7 new methods with their headers and body. After this, I created 12 unit tests to test the functionality of my web application. Later, I created a RESTful API to handle all the requests to the server, including 4 basic CRUD operations using different HTTP verbs. Finally, I connected my Node.js app with a MongoDB server and used the Googleapis to set up authentication on my website. I then uploaded everything to my production environment to make this RESTful API public.

### Design Overview
To begin with, my project had the following folder structure:

```
app/
├── models/
│   ├── Task.js
│   └── User.js
└── routes/
    ├── auth.js
    └── tasks.js
    └── user.js
util/
└── index.js
└── mongoose.js
└── passport.js
```


Each of the files inside of models/ were my Mongoose Schemas. I had a Task.js and a User.js, Schemas are used to validate data that will be passed off to the server, in my case, to my MongoDB server, basically the Schemas hold the data that will be passed to the server. This is an example of my Task.js Schema:

![image](https://github.com/Facuu35/MongoDB/assets/17630462/676d7eca-5139-4132-9a62-69ccbe58ebaa)


Moreover, to authenticate, I used a Google API to simplify the sign-in process. I created an account in Google Cloud and retrieved my keys, secret ID, etc., to use it on my website.

### UML


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
1. **Mismatch in Schema and Endpoint:** : My web app. Was not printing on the screen what it was supposed to, I spent at least two hours trying to figure out what the problem was, however, I realized that due to a capitalization error in one word it did not work. I was passing the following objects in my tasks.js “Text, userId, Done, Date” and in my schema I had “Text, UserId, Done, Date” the problem was in the lowercase letter “u” in my tasks.js. To avoid this from happening, I must make sure the objects are the same.
2. **Middleware Setup:** I was struggling with making my app work, It seemed like the app was turned off. I did not know what was wrong with it, I met with a tutor and they helped me identify that I wasn’t using:

![image](https://github.com/Facuu35/MongoDB/assets/17630462/33de4f32-3475-49d1-9076-fb478a2d42eb)

So the app would have never worked without these two lines. Together, these middleware functions set up Passport.js for user authentication and session management in a Node.js application.

4. **Unit Testing:** This was very hard to understand, I was very confused about my api.test.js, I thought I had to create more unit test cases, so I did and nothing seemed to be working, everything was broken. I met with a tutor and they guided me through what I was supposed to do. I learned that I could use the unit test cases from 4A, all I had to do was change the BaseUrl and the cookie, I also had to make modifications to my tasks.js to print errors when the user did not supply enough data or when the ID was invalid, after making changes to my endpoints the tests run perfectly fine. This is a snip of code I had to add to print the error:
 
![image](https://github.com/Facuu35/MongoDB/assets/17630462/d515a5e0-edc0-489e-ad35-bae4f3f50d29)


### Conclusion
•	I can create an RESTfulAPI and create mongoose schemas and endpoints in my web application

•	I can use Googleapis to authenticate users in my web application 

•	I can create unit tests to test my endpoint routes

•	I can move my development code to my production environment without any issues

### Resources
1. https://www.geeksforgeeks.org/mongoose-schemas-creating-a-model/
2. https://dev.to/yksolanki9/noobs-guide-to-using-any-google-api-in-nodejs-1j8g
3. https://www.passportjs.org/concepts/authentication/middleware/
4. https://www.passportjs.org/
