# Dockerfile for running python web apps with uWSGI

This Dockerfile allows you to build a Docker container with 
a fairly standard and speedy setup for Python web apps with uWSGI.

uWSGI from a number of benchmarks has shown to be the fastest server 
for python applications and allows lots of flexibility.

Feel free to clone this and modify it to your liking. And feel free to 
contribute patches.


### Before Build

- Replace the content of /app with the root of your django
project before build new docker image.

- uWSGI chdirs to /app so in uwsgi.ini you will need to make sure the python path
to the wsgi.py file is relative to that.
Suppose you want to create a Django application container and your `wsgi.py` file path is `/app/myproject/wsgi.py` 
then open uwsgi.ini and change `module=website.uwsgi:application` as `module=myproject.uwsgi:application`.


### Build and Run container
* docker build -t webapp .
* docker run -d webapp

