---
tags:
  - Docker
  - Data-Engineer
  - Python
  - Database
---

# 1.Introduction to Docker
1. Dockerfile:
```
FROM python:3.9.1

RUN apt-get install wget

RUN pip install pandas sqlalchemy psycopg2

WORKDIR /app

COPY ingest_data.py ingest_data.py

ENTRYPOINT [ "python", "ingest_data.py" ]
```
	- Dockerfile always starts with a available image by using FROM
	- RUN = sudo
	- WORKDIR is for create a directory
	- COPY -> copy from the outside to docker image
	- ENTRYPOINT is where docker will run 

2. [docker-compose.yaml][https://www.youtube.com/watch?v=hKI6PkPhpa0]
```
services:

  pgdatabase:

    image: postgres:13

    environment:

      - POSTGRES_USER=root

      - POSTGRES_PASSWORD=root

      - POSTGRES_DB=ny_taxi

    volumes:

      - '/var/lib/postgresql/data:/var/lib/postgresql/data'

    ports:

      - "5432:5432"

  pgadmin:

    image: dpage/pgadmin4

    environment:

      - PGADMIN_DEFAULT_EMAIL=admin@admin.com

      - PGADMIN_DEFAULT_PASSWORD=root

    ports:

      - "8080:80"
```
    
    - Use docker compose if you want to create multiple containers. For example with the above script, docker compose will generate 2 contains, 1 for postgres database and 1 for pgadmin, which connects to postgres. Using `docker compose up` will trigger docker to build all containers in docker-compose.
	-  For connecting two docker containers through a same network, we use `docker network create network-name`. For now you will have to rerun the containers again with one extra parameter `--network=network-name` 
	- I have a problem with mounting the directory to container. But i was easy to solve.
	
3. [Ingesting the data to database][https://www.youtube.com/watch?v=2JM-ziJt0WI&t=1310s]
	- For connect python to postgres database use `from sqlalchemy import create_engine`
	- If the data is too large, reading csv file with pandas chunk is a solution.
	
4. GCP ( On-going )