# Why does this image exists?

This image's only purpose is to provide django-admin functionality without any development environment/libraries installed directly on the main operative system.
 
The idea is that with many development projects running on my workstation it's painful to install and maintain different libraries and versions for each project. Virtualization or containerization to the rescue, but what about project generators and other setup script? To have django-admin.py you need to have setup python and django, but to do so you need to have already setup your development docker image, while sometimes I prefer to setup the directory structure a little beforehand.

With this image I can get in my development directory (where I will write the application dockerfile) and run: 

    docker run -t -i -v $(pwd):/app scotu/django:1.10.1-python3.5.2-alpine django-admin.py startproject project_name
