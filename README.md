# 13-Newsletter-Signup
THIS WEBSITE IS UNDER PROGRESS -> It's not complete like it's working perfectly fine on localhost:3000 but deplyoing it on heroku is still left. 
Made this NewsLetter signup with the help of JavaScript , using Express framework in Node.js 

-> What is MailChimp ??
1. Mailchimp offers integrations with various platforms and applications, allowing users to connect their email marketing efforts with other tools they use. It also provides APIs for developers to interact with Mailchimp programmatically and build custom integrations.
2. Mailchimp provides features for managing and organizing your subscriber data. You can import existing subscriber lists, add new subscribers manually, and segment your audience based on various criteria such as demographics or subscriber activity. Mailchimp also handles opt-ins and opt-outs, allowing subscribers to manage their preferences and unsubscribe if desired.

-> What is Heroku ??
Heroku is a cloud platform that allows developers to deploy, manage, and scale applications easily. It provides a platform-as-a-service (PaaS) solution, meaning it takes care of the underlying infrastructure and allows developers to focus on building and deploying their applications without worrying about server management.


CODE EXPLAINATION : 
1. Required Modules: The code requires several modules to be imported: express, body-parser, request, and https. These modules are used for creating a web server, parsing request bodies, making HTTP requests, and establishing secure connections.
2. Express App Setup: An instance of the Express application is created by calling express(). It is stored in the app variable.
3. Static Files: The express.static middleware is used to serve static files located in the "public" directory. This is useful for serving CSS, images, and client-side JavaScript files.
4. Body Parsing: The body-parser middleware is used to parse the request body in URL-encoded format. It allows access to form data sent in POST requests.
5. Route Handling: The app defines two routes:
6. The root route ("/") handles GET requests and sends the "signup.html" file as the response. This file is typically an HTML form where users can enter their information to sign up.
7. The root route ("/") also handles POST requests. It extracts the submitted form data (first name, last name, and email) from req.body and prepares a JSON payload for the Mailchimp API. It then sends an HTTPS request to the Mailchimp API endpoint ("/lists/90dbc88ee1") using the provided API key in the authorization header.
8. Mailchimp Integration: The code integrates with the Mailchimp API to subscribe users to a mailing list. It constructs the necessary data structure in the expected format and sends it as a JSON payload to the Mailchimp API endpoint. The API response is checked for a successful status code (200). If successful, the "success.html" file is sent as the response; otherwise, the "failure.html" file is sent.
9. Redirect Route: There is an additional route ("/failure") that handles POST requests. If the subscription fails, the user is redirected to this route, which in turn redirects them back to the root route ("/").
10. Server Startup: The app listens on the specified port (either the value of the process.env.PORT environment variable or port 3000) and logs a message to the console indicating that the server is running.
11. API Key and List ID: The Mailchimp API key and list ID are provided as comments in the code. These values are specific to your Mailchimp account and need to be replaced with your own API key and list ID.


-> In summary, this code sets up a web server using Express.js, handles form submissions, and integrates with the Mailchimp API to subscribe users to a mailing list. It demonstrates the process of making HTTP requests, handling responses, and performing server-side operations with external APIs.
