## String connect mongoDB

mongodb+srv://admingataria:admingataria@gataria-database.atmhlxw.mongodb.net/

## Running gataria via docker

sudo docker build -t gataria-backend-images:dev .

sudo docker run -d --name backend-images -e CATAPI_URL="https://api.thecatapi.com/v1/images/search" -p 3020:3020 gataria-backend-images:dev

sudo docker build -t gataria-backend-catalog:dev2 .

sudo docker run -d --name backend-catalog -e MONGO_DATABASE="dev" -e MONGO_URL="mongodb+srv://admingataria:admingataria@gataria-database.atmhlxw.mongodb.net/" -p 3010:3010 gataria-backend-catalog:dev2

sudo docker build -t gataria-frontend:dev .

sudo docker run -d --name frontend -p 3000:3000 gataria-frontend:dev

## Dockerhub

docker tag gataria-frontend:dev evermariano/gataria-frontend:dev
docker push evermariano/gataria-frontend:dev

docker tag gataria-backend-images:dev evermariano/gataria-backend-images:dev
docker push evermariano/gataria-backend-images:dev

docker tag gataria-backend-catalog:dev evermariano/gataria-backend-catalog:dev2
docker push evermariano/gataria-backend-catalog:dev2

