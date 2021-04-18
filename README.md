# Dockerised Django

This project aims to take a base
[Django template](https://github.com/django/django/tree/main/django/conf/project_template)
and put it inside a Docker container, runnable from `docker-compose`.

To get up and running with this template, install Docker Desktop (or Docker
Engine and `docker-compose` on Linux), and run the following command:

```sh
docker run --rm -v "$(pwd)":/code mattcen/djangobase \
  django-admin startproject --template https://github.com/mattcen/dockerised-django/archive/main.zip \
  --extension env PROJECT_NAME
```

Replace `PROJECT_NAME` with the chosen name of your project, and use the rest
of the command verbatim.

Note: The `mattcen/djangobase` container image is built using the Dockerfile
from this repo.

You should now have a subdirectory of your current directory with the name
`PROJECT_NAME` (i.e. the name you chose for your project).

`cd` into this directory and run `docker-compose up`, which should build your
project and make it available on http://localhost:8000 for you to test and
start developing.
