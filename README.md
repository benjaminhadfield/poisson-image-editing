# Poisson Image Editing

Poisson Image Edition implementation (Image Processing coursework).

> **Note**: Apologies about the spaghetti code, I was focussing more on the concepts and less on DRY principles and project structure in this coursework.

### Table of Contents

 - [Submission Details](#submission-details)
 - [Project Structure](#project-structure)
 - [Usage](#usage)
 - [Customisation](#customisation)
 - [Acknowledgements](#acknowledgements)

### Submission Details

##### Student details

| Student | Email | Student Number |
| ---- | ---- | ---- |
| Ben Hadfield | zchabjh@ucl.ac.uk | 1401907

##### Implementation details

| Language | Dependencies | OS
| ---- | ---- | ---- |
| Python 3 | Either [Python 3](https://www.python.org/downloads/) or [Docker](https://www.docker.com/) | Tested on MacOS and Linux |

_**Note**: Docker is the preferred way to run the project, since it doesn't
require you to manually download requirements._

### Project Structure

This project is split into two parts, a frontend, in `frontend/`, and a backend, in `backend/`.
The backend is a lightweight [Flask](http://flask.pocoo.org/) server. The Poisson implementation lives in the `backend/poisson/` directory.
The frontend is a simple [React](https://reactjs.org/) app that offers a visual interface for the implementation. Poisson editing can also be run programmatically using the API alone.

##### Poisson implementation

The actual algorithm implementations for each task can be found at `backend/poisson/tasks/task{i}.py`.

##### Other backend code

The task code makes use of common utility methods which can be found in the neighbouring folder at `backend/poisson/utils`. The utility code doesn't contain any poisson specific code, but rather helper methods for saving images and helper methods for PIL (an image library for python).

##### Demo Images

Three example results can be found in the `results/` folder.

### Usage

#### Docker

Using docker is the preferred way to run this project.

 - Install [Docker](https://docs.docker.com/docker-for-mac/install/)
 - Unzip the project and navigate to the project root in terminal
 - Run `docker-compose up`

The project is now running, open a browser and navigate to `localhost:3000` for the user interface.
Alternatively, you can use the API directly, which is accessible at `localhost:5000`.

Type `ctrl c` to stop the servers.

_**Note**: If you only want to run the backend server then you can type
`docker-compose run backend` instead of `docker-compose up`._

#### Python (with `pip`)

This method is slightly more involved, and will install all the project dependencies directly to your computer. You will need to install the dependencies for both the backend and the frontend.

_If you don't want to use the user interface then you can skip the frontend installation._

 - Unzip the project and navigate to the project root.

##### Install Backend

 - Navigate to the backend folder `cd ./backend`
 - Start a python virtual environment `python3 -m venv venv`
 - Activate the environment `source ./venv/bin/activate`
 - Install the requirements with `pip3 install -r requirements.txt`
 - Run the backend service `python3 app.py`

The API is now running at `localhost:5000`

##### Install Frontend

 - Install either [Yarn](https://yarnpkg.com/lang/en/docs/install/) or [NPM](https://docs.npmjs.com/getting-started/installing-node)
 - Navigate to the frontend folder `cd ./frontend`
 - Install the dependencies with `yarn` or `npm install`
 - Run the frontend service with `yarn start` or `npm start`

The frontend is now running at `localhost:3000`

### Customisation

You can use your own images with this implementation.
All images used by the algorithm are stored in the `backend/static/` folder.
To use your own image, just put it in this directory.

There is one important restriction on the images, however.
All images must have the dimensions `600px × 399px` (width `600px`, height `399px`).
This is due to a limitation with this implementation of the algorithm.

### Acknowledgements

All images are taken from [Unsplash](https://unsplash.com/).
