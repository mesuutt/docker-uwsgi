# Dockerfile for running python web apps with uWSGI

This Dockerfile allows you to build a Docker container with 
a fairly standard and speedy setup for Python web apps with uWSGI.

uWSGI from a number of benchmarks has shown to be the fastest server 
for python applications and allows lots of flexibility.

Feel free to clone this and modify it to your liking.


### Before Build

- Add your python app to `/app` directory before build new docker image.

-  Check `module` config in uwsgi.ini: If you want to create a Django application container and your `wsgi.py` path is `/app/myproject/wsgi.py`, 
open uwsgi.ini file and change `module=website.uwsgi:application` as `module=myproject.uwsgi:application`.


### Build and Run container

- docker build -t myapp .
- docker run myapp

