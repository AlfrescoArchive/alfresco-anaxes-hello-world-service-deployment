# Welcome

This project contains the artifacts to deploy the [Hello World Service](https://github.com/Alfresco/alfresco-anaxes-hello-world-service) via Docker and Kubernetes.

The service connects to a Postgres database to retrieve the welcome message to return.

# Build

To build the Docker image run the script which gets the service jar:

    ./build-prep.sh

then:

    docker build -t anaxes-hello-world-service .

# Run

TODO