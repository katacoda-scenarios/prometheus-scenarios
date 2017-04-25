With the containers launched, Prometheus will scrape and store the data based on the internals in the configuration.

## Dashboards

The default Prometheus Dashboard reports internal information and provides a way to debug the metrics being collected. The dashboard can be viewed [here](https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/)

The dashboard will report the status of the scraping and the different targets at via the [/targets](https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/targets) page.

When running in production, you may wish to build a dashboard using [Grafana](https://grafana.com/), or a hosted Prometheus instance such as [Weave Cortex](https://www.weave.works/solution/prometheus-monitoring/).

## Query Prometheus

To query the underlying metrics and create graphs, visit the graph page on the Dashboard at https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/graph

From here different metrics are queryable based on their name.

For example, querying for `node_network_receive_bytes`{{copy}} will show how active the disk IO is. Querying using `node_cpu`{{copy}} will output the Docker Hosts CPU information.

All the metrics scraped from [the metrics endpoint](https://[[HOST_SUBDOMAIN]]-9100-[[KATACODA_HOST]].environments.katacoda.com/metrics) are viewable.
