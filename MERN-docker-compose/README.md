# A simple MERN stack application 

### Create a network for the docker containers

`docker network create demo`

### Build the client 

```sh
cd mern/frontend
docker build -t mern-frontend .
```

### Run the client

`docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend`

### Verify the client is running

Open your browser and type `http://localhost:5173`

### Run the mongodb container

`docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest`

### Build the server

```sh
cd mern/backend
docker build -t mern-backend .
```

### Run the server

`docker run --name=backend --network=demo -d -p 5050:5050 mern-backend`

## Using Docker Compose

`docker compose up -d`

## Docker Compose: 

![docker-compose](https://github.com/user-attachments/assets/67ac3477-d80e-416c-a69e-258b2caa1d11)

## Step-by-Step process build and runnning seprately 

![Run the application-1](https://github.com/user-attachments/assets/23b53b86-623b-4567-98e1-f1b002c49986)
![Run the application-2](https://github.com/user-attachments/assets/6f626100-af8d-4b2d-9eb1-2776032036ea)


## SS:
![multiple-records](https://github.com/user-attachments/assets/46ecb73f-54c8-4d5d-b692-77d5a86bd4a4)

## Mongo Image running:
![mogo-image](https://github.com/user-attachments/assets/c4d7eaee-d8fa-41e5-8f18-c343aa70e95a)

## Edited the employee to see if it's working.
![edited](https://github.com/user-attachments/assets/8164927f-f170-44b7-ac75-b527772ee225)

![record-saved](https://github.com/user-attachments/assets/396e4bec-914f-4ea4-a7f9-e48ef959a069)


