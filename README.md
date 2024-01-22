# DockerFlow
This is a Node/Express project where I used Docker to build and deploy the Backend API for a Blog Post Application

Building a Node/Express app with a Mongo & Redis database.
- Node/Express: used for building the backend API /api/v1
- Mongo DB: for storing data for CRUD operations.
- Redis DB: for storing cookies and authentication.

## Installation
Install docker according to your OS and pull the code repo.

## Usage

```bash

# To run the containers in the dev stack using docker-compose
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d --build -V

# To run the containers in prod stack using docker swarm
docker swarm init --advertise-add <IP_Address>
<IP_Address> - this is the system IP address where you want to run the docker containers

docker stack deploy -c docker-compose.yml -c docker-compose.prod.yml <Stack_Name>

```
## Test

Open Postman or any API testing tool.

To test the index.js 
http://localhost:3000/api/v1/

To SignUp
http://localhost:3000/api/v1/users/signup
{
    "username": "user",
    "password": "pass"
}

To Login
http://localhost:3000/api/v1/users/login
{
    "username": "user",
    "password": "pass"
}

To Post a Blog
http://localhost:3000/api/v1/posts
{
    "title": "This is the Post Title",
    "body": "This is the Post body"
}

To Get a Blog
http://localhost:3000/api/v1/posts/id_of_post

