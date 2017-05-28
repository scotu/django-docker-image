# Django Docker Image

This repo contains the dockerfile for a Django docker image. If you are building your own Django based app I suggest you start `FROM python` in your dockerfile instead of using this image. This image is useful if you want to run django-admin.py without installing django first. Read below for more details

## Why does this image exists?

This image's only purpose is to provide django-admin functionality without any development environment/libraries installed directly on the main operative system.
 
The idea is that with many development projects running on my workstation it's painful to install and maintain different libraries and versions for each project. Virtualization or containerization to the rescue, but what about project generators and other setup script? To have django-admin.py you need to have setup python and django, but to do so you need to have already setup your development docker image, while sometimes I prefer to setup the directory structure a little beforehand.

With this image I can `cd` in my development directory (where I will write the application Dockerfile) and run: 

    docker run -t -i -v $(pwd):/app scotu/django:1.11.1-python3.6.1-alpine django-admin.py startproject project_name

to generate my project files before writing my app's real Dockerfile
