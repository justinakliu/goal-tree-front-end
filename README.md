# GoalTree

## Problem Space
Popular to-do list apps help us manage tasks but don't help us create a comprehensive to-do list from a goal. What is the point of completing to-do lists that don't help us reach our end goals?

I created GoalTree to bridge the gap between big-picture planning and task management. 

- Users can build a tree from a goal by continuously dividing the goal into subgoals
- Users can generate to-do a list for a goal, which aggregates all the leaf nodes of the corresponding tree
- Users can easily toggle between tree view and list view; edits made on either view will be reflected on the other <br>
 
## Technologies
* Frontend: Javascript, React, D3.js, HTML, CSS, Chakra UI
* Backend: Python, Flask, SQL, PostgreSQL, SQLAlchemy [(visit backend repo here)](https://github.com/justinakliu/goal-tree-back-end)
* Deployed to Heroku: [Try out the app here!](https://goal-tree.herokuapp.com/)

## Features

### Home Page
- Displays all of a user's goals as well as their priority tasks
- Users can create, delete and update goals and check off tasks from their priority list
- Goal color reflects the completion status

<br>

![GIF1_new](https://user-images.githubusercontent.com/87151448/219982947-8ec8ea85-06d3-464a-b644-4e96988f0c3a.gif)

### Tree View 
- Users navigate to the tree and list views of a goal by clicking on the corresponding button
- Users can build a goal tree for a goal by adding subgoals, as well as delete and update existing nodes

<br>

![gif2](https://user-images.githubusercontent.com/87151448/219982777-304e6f1f-6d8a-44ee-b94b-4154d9181c52.gif)

<br>

- Users can update the completion status of a subgoal and see how the update affects the entire tree (this is the feature I'm most proud of! I implemented it using two recursive functions on the backend to update up and down the tree, starting from the updated node)

<br>

![gif4](https://user-images.githubusercontent.com/87151448/219983407-8c9f9130-303a-4aae-b919-83bdd84add7e.gif)

### List View
- User can toggle back and forth between tree and list view (generated by aggregating leaf nodes of a goal tree)
- Users can update the completion status of tasks; all changes made in list view are reflected in tree view and vice versa
- Users can also star a task to add it to their list of priority tasks   

<br>

![gif3](https://user-images.githubusercontent.com/87151448/219983099-4c66ed4f-2c60-4602-9e35-0c69bc3e07b0.gif)

## Set Up

To run this project on your local computer, follow the instructions below.

### Backend Set Up

Start by cloning the backend repo.
```
git clone https://github.com/justinakliu/goal-tree-back-end.git
```
Create and activate a virtual environment inside your directory
```
python3 -m venv venv
source venv/bin/activate
```
Install the dependencies:
```
pip install -r requirements.txt
```
Create a database for the application and a .env file. In the .env file, create an environment variable called `SQLALCHEMY_DATABASE_URI` to hold the path to your database. Your .env file might look like:

```
SQLALCHEMY_DATABASE_URI=postgresql+psycopg2://postgres:postgres@localhost:5432/goal_tree_database
```
To finish setting up your local database, run:
```
flask db upgrade
```
And finally, to run the backend app:
```
flask run
```

### Frontend Set Up

Clone the frontend repo in a separate directory.

```
git clone https://github.com/justinakliu/goal-tree-front-end.git
```

Install the dependencies:

```
npm install
```

Run the app:

```
npm run dev
```
<br>

You can now access GoalTree at 'localhost:3000/'!


