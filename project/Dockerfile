FROM python:3.13.3-slim

WORKDIR /app

RUN apt-get update && apt-get install -y --no-install-recommends \
    libpq-dev \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get -qq update

RUN apt-get install -y gdal-bin libgdal-dev

RUN pip install setuptools

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

EXPOSE 8000

# CMD sh -c " \
#     python manage.py migrate && \
#     python manage.py runserver 0.0.0.0:8000 \
# "
# RUN python manage.py migrate

#CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]