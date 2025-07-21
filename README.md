## Docker-based GeoDjango app (PostrGIS DB) with Celery setup

This is just a boilerplate django app for geospatial application that battery-include postgis and celery already. Geospatial engineer will not waste the time to setup the GeoDjango system with some conplicated PostGIS database and Celery tools.

## Get started

1. Clone this repo
```
git clone https://github.com/thanthamky/django-celery-docker.git
```

5. Change `.env` settings. Create a folder somewhere to link with large storage for store file-based resourcesl. For example:

```
STORE_DIR=/home/$USER/store
```

7. Run compose

```
docker compose up -d
```

6. Create admin user
```
docker exec -it <project_name>_django /bin/bash
python manage.py createsuperuser

# follow the instruction to create admin account
```
