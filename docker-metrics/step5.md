With the containers launched, Prometheus will scrap and store the data based on the internals in the configuration.

## Dashboards

The default Prometheus Dashboard reports internal information and provides a way to debug the metrics being collected. The dashboard can be viewed [here](https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/)

The dashboard will report the status of the scraping and the different targets at via the [/targets](https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/targets) page.

When running in production, you may wish to build a dashboard using [Grafana](https://grafana.com/), or a hosted Prometheus instance such as [Weave Cortex](https://www.weave.works/solution/prometheus-monitoring/).

## Query Prometheus

To query the underlying metrics and create graphs, visit the graph page on the Dashboard at https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/graph

From here different metrics are queryable based on their name.

For example, querying for **engine_daemon_container_actions_seconds_sum** will show how many Docker actions are being performed. These actions are containers being started, deleted, created, committed, or changed.

The host metrics can be viewed too, for example, **node_cpu** will output the Docker Hosts CPU information.

## Generate Metrics

Running additional containers will result in changes to the metrics produced, which are viewable via the graphs and queries.

`docker run -d katacoda/docker-http-server:latest`{{execute}}
