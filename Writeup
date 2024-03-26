# Facundo Fernandez - Lab Report

## Date: 03/25/2024
## Lab Title: Node.js and Unit Testing – REST API in Node.js

### Summary
In these two labs, I worked with Node.js to create the structure of a web application. To begin with, I had to set up Node and install the dependencies. Then, I wrote 7 new methods with their headers and body. After this, I created 12 unit tests to test the functionality of my web application. Later, I created a RESTful API to handle all the requests to the server, including 4 basic CRUD operations using different HTTP verbs. Finally, I connected my Node.js app with a MongoDB server and used the Googleapis to set up authentication on my website. I then uploaded everything to my production environment to make this RESTful API public.

### Design Overview
To begin with, my project had the following folder structure:




Each of the files inside of `models/` were my Mongoose Schemas. For example, `Task.js` defined the schema for tasks that will be passed to the server. Inside of the `routes` folder, I had three files: `auth.js`, `users.js`, and `tasks.js`, which represented my endpoints. These endpoints had method handlers to create, read, update, and delete. The endpoints matched their corresponding Schema objects.

Moreover, to authenticate, I used a Google API to simplify the sign-in process. I created an account in Google Cloud and retrieved my keys, secret ID, etc., to use it on my website.

### UML
[Insert UML diagram here]

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
