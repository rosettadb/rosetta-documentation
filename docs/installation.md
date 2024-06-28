
The quickest way to deploy Rosetta is to utilize the latest Docker image. This Docker image contains all the necessary dependencies required to run Rosetta.

To initiate the Rosetta Docker container, simply execute the following Docker command:

```
docker run -p 8080:8080 -e ACCEPT_EULA=Y adaptivescale/rosetta-ce:latest
```

This command will retrieve the Docker image with the most recent published version of Rosetta.

The `ACCEPT_EULA` env variable is mandatory for confirming your acceptance of the End-User Licensing Agreement.

Once the Docker image is deployed, Rosetta can be accessed via a browser using the following link:
[http://localhost:8080/](http://localhost:8080/)

One of the dependencies of Rosetta is ElasticSearch, which is currently bundled inside. You can configure a container to connect to an external ElasticSearch instance by setting the following environment variable: `ADAPTIVESCALE_ELASTIC_HOST`. An example of how to set it is below:

```
docker run -p 8080:8080 -e ADAPTIVESCALE_ELASTIC_HOST=http://localhost:9200 adaptivescale/rosetta-ce:latest
```

Rosetta comes with a default username set as `admin` and a password set as `admin`. However, you can change these credentials by providing the following environment variables: `PROEDMS_USER` and `PROEDMS_PASSWORD`. Here's an example of how to use this:

```
docker run -p 8080:8080 -e PROEDMS_USER=testuser -e PROEDMS_PASSWORD=testpassword adaptivescale/rosetta-ce:latest
```
