Fast Data - Ingest - Pull
=========================

Purpose
-------
Pull data from defined source and ingest it into Kafka Broker.

Properties
----------
- Pull Url (String)
- PullDuration (Int)
- Kafka ClientId (String)
- Kafka BootstrapServer (String: host:port,host:port)
- Kafka Topic (String)

Run the Job
===========

Variant a)
----------
Starting the application with "java -jar ..." and passing configuration params on commandline:

```
&> java -jar fd-ingest-pull-<VERSION>.jar de.khive.fastdata.ingest.pull.IngestApplication <pull_url> <pull_duration_seconds> <kafka_client_id> <kafka_bootstrap_server> <kafka_target_topic>
```

Use Case: Run application from commandline as an unix service

Variant b)
----------
Starting the application with "java -jar ..." and passing configuration params in environment variables:

```
&> export FD_INGEST_PULL_URL="<url>"
&> export FD_INGEST_PULL_DURATION=<pull_duration_seconds>
&> export FD_INGEST_KAFKA_CLIENTID="<clientId>"
&> export FD_INGEST_KAFKA_BOOTSTRAP_SERVER="host1:port,host2:port"
&> export FD_INGEST_KAFKA_TOPIC="<topic>"
&> java -jar fd-ingest-pull-<VERSION>.jar de.khive.fastdata.ingest.pull.IngestApplication 
```

Use Case: Run application from inside a docker container and pass environment variables for example through mesosphere marathon configuration