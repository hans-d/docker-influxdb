docker-influxdb
=====================

InfluxDB image

    
Tags
----

    latest -> 0.9.2
    0.9    -> 0.9.2

    0.9.2  -> 0.9.2
    0.9.1  -> 0.9.1

Running
-------

Start your image binding the external ports `8083` and `8086` in all interfaces to your container. 

    docker run -d -p 8083:8083 -p 8086:8086 hansd/influxdb


Configuring your InfluxDB
-------------------------
Open your browse to access `localhost:8083` to configure InfluxDB. Fill the port which maps to `8086`. The default credential is `root:root`. Please change it as soon as possible.

Alternatively, you can use RESTful API to talk to InfluxDB on port `8086`


Initially create Database
-------------------------
Use `-e PRE_CREATE_DB="db1;db2;db3"` to create database named "db1", "db2", and "db3" on the first time the container starts automatically. Each database name is separated by `;`. For example:

```docker run -d -p 8083:8083 -p 8084:8084 -e PRE_CREATE_DB="db1;db2;db3" hansd/influxdb:latest```

