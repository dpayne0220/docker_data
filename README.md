# docker_data

This is a docker data container used for linking directory structure to web server containers


used in derpal this container can be initialized like this
docker build -t uname/docker-data .

docker run --name myapp-data -v /Users/dylan/myapp:/data:rw uname/drupal-data

the run like
docker run uname/drupal-data



it is linked by running 

docker run -d -p 8000:80 --volumes-from myapp-data iiiepe/nginx-drupal




docker run -d -p 8000:80 --volumes-from myapp-data --link mariadb iiiepe/nginx-drupal
