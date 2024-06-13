
# Heroku + React To-Do List

This is a React app that deploys a to-do list application on Heroku. It allows users to manage their tasks efficiently and is built using Create React App.

## Installation

Before cloning the project, make sure you have Node.js and npm installed on your machine. Additionally, you need to create a Heroku account if you haven't already.

### Clone this repo

```sh
git clone <repo_url>
cd <repo_directory>
```

### Install dependencies

In the project directory, run the following command to install the necessary dependencies:

```sh
npm install
```

### Create a Heroku app

Go to the Heroku website and log in to your account. Create a new app by following these steps:

1. Click the "New" button and select "Create new app".
2. Name your app and choose your region.
3. Click "Create app".

### Set up Heroku for deployment

Install the Heroku CLI if you haven't already:

```sh
curl https://cli-assets.heroku.com/install.sh | sh
```

Log in to Heroku from the command line:

```sh
heroku login
```

Add the Heroku remote to your project:

```sh
heroku git:remote -a <your_heroku_app_name>
```

### Configure environment variables

In the project directory, create a `.env` file to store your environment variables. Add the following lines to configure the environment:

```
REACT_APP_API_URL=<your_api_url>
```

### Deploy the app to Heroku

Build the app:

```sh
npm run build
```

Deploy the app to Heroku:

```sh
git add .
git commit -m "Deploy to Heroku"
git push heroku master
```

### Open the app

Once deployed, you can open your app in the browser:

```sh
heroku open
```

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in development mode. Open [http://localhost:3000](http://localhost:3000) to view it in the browser. The page will reload if you make edits. You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode. See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder. It correctly bundles React in production mode and optimizes the build for the best performance. The build is minified and the filenames include the hashes. Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

## API Paths

### Tasks

- **GET /tasks**: Retrieve all tasks.
- **POST /tasks**: Create a new task.
- **PUT /tasks/:id**: Update an existing task.
- **DELETE /tasks/:id**: Delete a task.

## Stopping the App

To stop the development server, press `Ctrl + C` in the terminal where `npm start` was run.

## Rebuilding the App

To rebuild the app after making changes:

1. Stop the current instance (if running):

   ```sh
   heroku ps:scale web=0
   ```

2. Build the app:

   ```sh
   npm run build
   ```

3. Deploy the changes:

   ```sh
   git add .
   git commit -m "Rebuild and deploy"
   git push heroku master
   ```

4. Restart the Heroku app:

   ```sh
   heroku ps:scale web=1
   ```