https://dev.to/karanpratapsingh/dockerize-your-react-app-4j2e


https://docs.docker.com/engine/reference/commandline/build/

docker build -f dockerfiles/Dockerfile.prod  -t myapp_prod .


docker tag  2084f3d3b4c5 tmacshit1/create-react-demo:1.0
docker push tmacshit1/create-react-demo:tagname
