```
mkdir -p /prometheus/data
docker run -d --net=host \
    -v /home/scrapbook/tutorial/prometheus.yml:/etc/prometheus/prometheus.yml \
    -v /prometheus/data:/prometheus \
    --name prometheus-server \
    prom/prometheus
```{{execute}}


```
docker run -d \
  -v "/proc:/host/proc" \
  -v "/sys:/host/sys" \
  -v "/:/rootfs" \
  --net="host" \
  --name=promethus \
  quay.io/prometheus/node-exporter:v0.13.0 \
    -collector.procfs /host/proc \
    -collector.sysfs /host/sys \
    -collector.filesystem.ignored-mount-points "^/(sys|proc|dev|host|etc)($|/)"
```{{execute}}
