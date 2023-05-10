# Docker-images

## ubuntu-http-server
Checkout the dockerfile provided along with this.  
A docker image having ubuntu as OS and apache2 installed. You can do changes as per your needs. To build the docker file, do:
```
docker build -t <img_name> -f <docker_file> .
```

You have to bind the port of the image after building it. To do that, use:

```
docker run -d -p 8080:80 <image_name>
```

If you don't want to include a Dockerfile in your project, it is sufficient to do the following:  
  
For Windows :
```
docker run -itd --rm --name my-apache-server -p 8080:80 -v "%CD%":/var/www/html/ -w /var/www/html akshatkhatod/ubuntu_http_img
```

For Linux :
```
docker run -itd --rm --name my-apache-server -p 8080:80 -v "$PWD":/var/www/html/ -w /var/www/html akshatkhatod/ubuntu_http_img
```

It connects with the index.html file saved on your present working directory. Go to localhost:<port_no> (in this case localhost:8080) to check if the server is working and see any changes done in the index.html file. That's all, your http server is up and running.
Thank You
