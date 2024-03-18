## Node and React Deployed with Multiple Containers

**Multiple Container App Each container interact with other container and live source code updates and data persist**

- In frontend directory run `docker build -t goals-frontend .`

- In backend directory run `docker build -t goals-backend .` 

- `docker network create goals`

- `docker run -d --rm -v data:/data/db --network goals --name mongodb -e MONGO_INITDB_ROOT_USERNAME=ahmad -e MONGO_INITDB_ROOT_PASSWORD=secret mongo`

- `docker run --rm --name goals-api -v /home/ahmad/Desktop/Development/projects/fullstack01/backend:/app -v logs:/app/logs -v /app/node_modules  -d  -p 80:80 --network goals goals-backend`

- `docker run --name goals-react -v /home/ahmad/Desktop/Development/projects/fullstack01/frontend/src:/app/src  --rm -d -p 3000:3000 goals-frontend`
