Prometheus can run as a Docker Container with a UI available on port _9090_. Prometheus uses the configuration to scrape the targets, collect and store the metrics before making them available via API that allows dashboards, graphing and alerting.

## Task

The following command launches the container with the prometheus configuration. Any data created by prometheus will be stored on the host, in the directory /prometheus/data. When we update the container, the data will be persisted.

```
mkdir -p /prometheus/data
docker run -d --net=host \
    -v /home/scrapbook/tutorial/prometheus.yml:/etc/prometheus/prometheus.yml \
    -v /prometheus/data:/prometheus \
    --name prometheus-server \
    prom/prometheus
```{{execute}}

Once started, the [dashboard](https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/) is viewable on port [9090](https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/). The next steps will explain the details and how to view the data.
