Step 1: Setting up the Flask Backend First, we begin by setting up the backend using Flask. Create a new directory for your project and within it, create a new Python file for your Flask application. For instance, you can name it app.py. In this file, import Flask and set up a basic route

Step 2: Creating the Backend Application Next, you can define more complex routes for your application that handle data storage and retrieval. For instance, you might want to create a register route that allows new users to sign up for your application. Here’s how you could implement this: This endpoint receives user information, checks if the user already exists in the database, and if not, inserts the new user into the database and generates a token medium.com.

Step 3: Setting up the React Frontend Once the backend is set up, you can start creating the frontend using React. First, create a new React application using the command npx create-react-app your-app-name. This will create a new directory with a basic React application structure. Replace the default App.js file with your own. Here's a simple example of a React component.

Step 4: Making HTTP Requests from React to Flask Now that you have a working React app, you can use it to interact with your Flask backend. Let’s see how to fetch data from the /register endpoint that we created earlier. To do so, you can use the fetch function in your React component to make an HTTP request to your Flask backend.

Step 5: Running the Full Stack Application Finally, you can run your full stack application. Start your Flask server by running python app.py in your terminal. Then, start your React application by navigating to your React application directory in a new terminal window and running npm start. Now, you can view your full stack application by navigating to http://localhost:3000 in a browser.
I have a frontend app written in React (plain CRA project) that uses a backend written in Python using Flask.

I'd like to set up the project in the following way:

In production: The backend serves the optimized frontend build on path /. The endpoints used by the frontend are registered on other paths on the same server.

In development I run the apps separately (using npm run start and flask --app=app.py run) in order to take advantage of the tooling provided by CRA. This means that the frontend and backend run on different ports on localhost, so the frontend must be told where the backend is. So the backend does not serve the frontend in dev.

The way I'm thinking to achieve this is using environment variables:

Frontend: BACKEND_URL_BASE specifies the URL base of the backend. It's empty in production and non-empty in dev.
Backend: FRONTEND_PATH specifies the location of the static files produced by npm run build.
