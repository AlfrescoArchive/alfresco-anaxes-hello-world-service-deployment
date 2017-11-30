# Welcome

This project contains the artifacts to deploy the [Hello World Service](https://github.com/Alfresco/alfresco-anaxes-hello-world-service) via Docker and Kubernetes.

The service connects to a Postgres database to retrieve the welcome message to return.

# Build Docker Image

To build the Docker image run the script which gets the service jar:

    ./build-prep.sh

then:

    docker build -t anaxes-hello-world-service .

# Run Docker Image

You first need the postgres host.  If you run postgres via Docker and have named the container 'postgres' you can run:

    docker inspect -f "{{ .NetworkSettings.IPAddress }}" postgres

Then run the service Docker image on port 8080:

    docker run -p8080:8080 -e SPRING_DATASOURCE_URL=jdbc:postgresql://<postgres-host>/postgres -e SPRING_DATASOURCE_USERNAME=postgres anaxes-hello-world-service:latest

# Helm

See [helm/hello-world-service](helm/hello-world-service)