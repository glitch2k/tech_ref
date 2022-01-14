# BUILD A DRUPAL & POSTGRES STACK USING DOCKER-COMPOSE

build a docker-compose file to deploy a **Drupal** content mgmt
    system connected to a **Postgres** database


- **DRUPAL**
  - expose port **8080** on drupal server

  - during the drupal configuration process, ensure that the it knows
  that the database to use is **NOT** localhost but the service name
  of the postgres container

  - use a persistant docker volume to store the **system config  data** data of the
    drupal server



- **POSTGRES**
  - set the default password for the postgres server to the following
  env var
    - POSTGRES_PASSWORD

  - use a persistant docker volume to store the **drupal content
    data** on the server
