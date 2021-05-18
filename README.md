# Docker Image with Telegraf (StatsD), InfluxDB and Grafana

Supports metrics via UDP on port 8125 and TCP on port 8126

## tl;dr

Build Docker image:

```sh
docker build -t metrics:latest .
``` 

Run the image:

```sh
docker run --ulimit nofile=66000:66000 \
  -d \
  --name metrics \
  -p 3003:3003 \
  -p 3004:8888 \
  -p 8086:8086 \
  -p 8125:8125/udp \
  -p 8126:8126 \
  metrics:latest
```

Open <http://localhost:3003> to see Grafana.

Credentials: `root`, `root`
