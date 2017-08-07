### spark-standalone-docker

How to run standalone docker with one command:

1. run docker compose

```
docker-compose up -d
```
1.(optional) Check logs:
```
docker-compose logs -f
```

**And that's all! Spark standalone is running with 2 workers.**


You can easily add new worker based on your requirements.

By default this docker-compose has only two workers and 1 master.

Add new worker:
```
  spark-worker3:
   image: spark-worker
   ports:
   - "8083:8081"
   depends_on:
   - spark-master
```
and again `docker-compose up -d`


You can open `http://localhost:8080/` to get into spark master UI.

![spark master UI](/resources/spark-master-ui.PNG)