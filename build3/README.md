# Dockerfile for Drupal

``` bash
$ docker build -t test .
$ docker run -p 8080:80 --name drupal -d test
```

Then access http://localhost:8080 to install Drupal.
