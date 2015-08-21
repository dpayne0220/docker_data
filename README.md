# docker_data

This is a docker data container used for linking directory structure to web server containers


used in derpal this container can be initialized like this
docker build -t uname/docker-data .

docker run --name myapp-data -v /Users/dylan/myapp:/data:rw uname/drupal-data

the run like
docker run uname/drupal-data



it is linked by running 

docker run -d -p 8000:80 --volumes-from myapp-data iiiepe/nginx-drupal


how to create a mariadb container

docker run --name some-mariadb -e MYSQL_ROOT_PASSWORD=mysecretpassword -d mariadb

how to run with mariadb support


docker run -d -p 8000:80 --volumes-from riot-data --link mariadb iiiepe/nginx-drupal


last command for debugging

 docker run -i -t -p 8000:80 --volumes-from riot-data --link riot-mariadb iiiepe/nginx-drupal
