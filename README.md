# DockerTemplate
Some Docker templates. Install [Docker](http://docs.docker.com/) here.

## For Mac User
1. Start Docker Quickstart Terminal, **OR** create a docker machine and set environment variables.
  
  ```
  $ docker-machine create --driver virtualbox default
  $ eval $(docker-machine env default)
  ```

2. Build the image 
  
  ```
  $ cd nodejs
  $ docker build -t mynodejs .
  ```

3. Run the image and expose 8080 port of the docker machine

  ```
  $ docker run -d -p 8080:8080 mynodejs
  ```
  
4. Test the image

  ```
  $ curl -i $(docker-machine ip default):8080
  HTTP/1.1 200 OK
  X-Powered-By: Express
  Content-Type: text/html; charset=utf-8
  Content-Length: 12
  Date: Wed, 09 Dec 2015 03:25:15 GMT
  Connection: keep-alive
  
Hello world
  ```

