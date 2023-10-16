Step-1: Run the base Nginx container
Access the URL http://localhost

docker run --name mynginxdefault -p 80:80 -d nginx
docker ps
docker stop mynginxdefault
Step-2: Create Dockerfile and copy our customized index.html
Dockerfile

FROM nginx
COPY index.html /usr/share/nginx/html
*index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=h1, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>Hello World from Docker</h1>
</body>
</html>

Step-3: Build Docker Image & run it

docker build -t rickyurvina/mynginx_image1:v1 .
docker run --name mynginx1 -p 80:80 -d rickyurvina/mynginx_image1:v1

Replace your docker hub account Id
docker build -t <your-docker-hub-id>/mynginx_image1:v1 .
docker run --name mynginx1 -p 80:80 -d <your-docker-hub-id>/mynginx_image1:v1

Step-4: Tag & push the Docker image to docker hub

docker images
docker tag rickyurvina/mynginx_image1:v1 rickyurvina/mynginx_image1:v1-release
docker push rickyurvina/mynginx_image1:v1-release

Replace your docker hub account Id
docker tag <your-docker-hub-id>/mynginx_image1:v1 <your-docker-hub-id>/mynginx_image1:v1-release
docker push <your-docker-hub-id>/mynginx_image1:v1-release