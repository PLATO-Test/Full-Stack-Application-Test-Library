# Full Stack App with React and a REST API

This project is a Full Stack React application utilising the [School Database REST API built in a previous project.](https://github.com/alexhippo/rest-api-sql-v3) Users can use the web interface built with React to:
- sign up
- sign in
- view courses
- create a course (if signed in)
- update their own courses (if authorised)
- delete their own courses (if authorised)

This app was implemented according to the designs specified in the `/mockups` and `/markup` folder.

## Motivation
This project was created to empower testers at Plato. This full-stack application allows our consultants to practice testing methodologies and test automation frameworks. Tests will be written in different frameworks and languages so that consultants at Plato can follow templates for automation test frameworks or practice manual test cases based on heuristic cheat sheets. This enables consultants to be competent and knowledgeable while working on client projects.

## Running the Application
1. Ensure that Docker is installed on your PC.
2. Run the following command in the root directory of the project:
```bash
   docker-compose up --build
```
3. To stop and remove all containers, run:
```bash
   docker-compose down
```
4. To stop containers and delete all data including volumes, run:
```bash
   docker-compose down -v
```
