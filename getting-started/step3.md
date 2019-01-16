To collect metrics related to a node it's required to run a Prometheus Node Exporter. Prometheus has many exporters that are designed to output metrics for a particular system, such as Postgres or MySQL.

## Task

Launch the Node Exporter container. By mounting the host /proc and /sys directory, the container has accessed to the necessary information to report on.

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

If you're interested in seeing the raw metrics, they can be viewed with `curl localhost:9100/metrics`{{execute}}
