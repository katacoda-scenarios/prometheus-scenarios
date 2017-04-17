The first task is to enable the new _experimental_ flag that will enable the metrics feature and define the metrics address to listen on _localhost:4444_.

The command below will update the systemd configuration used to start Docker to set the flags when the daemon starts and then restarts Docker.

```
sed -i 's/dockerd/dockerd --experimental --metrics-addr localhost:9323/g' /etc/systemd/system/docker.service
systemctl daemon-reload
systemctl restart docker
```{{execute}}

The metrics endpoint will be accessible once Docker has begun. You can see the raw metrics using `curl localhost:9323/metrics`{{execute}}

These metrics are outputted in the Prometheus format and designed to be scraped by a Prometheus server which will launch in the next steps.
