# InfluxDB v2

InfluxDB is an open source time series database. It has everything you need from a time series platform in a single binary – a multi-tenanted time series database, UI and dashboarding tools, background processing and monitoring agent. All this makes deployment and setup a breeze and easier to secure. 

**[Website](https://www.influxdata.com/)** | **[Documentation](https://docs.influxdata.com/influxdb/latest/)** | **[GitHub](https://github.com/influxdata/influxdb)**

## How to enable?

```
platys init --enable-services INFLUXDB2
platys gen
```

## How to use it?

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:19999> and login with user `influx` and password `abc123abc123!`. 
=======
Navigate to <http://10.156.72.251:19999> and login with user `influx` and password `abc123abc123!`. 
>>>>>>> Stashed changes

### InfluxDB CLI

The CLI can be used with `docker exec` command

```bash
docker exec -ti influxdb2 influx -h
```

To use the InfluxQL interactive shell to execute InfluxQL queries with InfluxDB v2

```bash
docker exec -ti influxdb2 influx v1 shell
```