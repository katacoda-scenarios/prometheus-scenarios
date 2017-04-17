With Docker 1.13, they introduced an experimental feature that allows the Docker Engine metrics to be exported using the Prometheus syntax.

Prometheus is an open source monitoring system and time series database. It's defined to collect metrics from multiple sources, such as the Operating System, MySQL or ElasticSearch, across multiple servers within your clusters. These metrics can then be graphed and displayed on a dashboard using Prometheus itself or tooling such as Grafana.

The Docker Engine metrics will include a number of containers started, stopped, created and deleted. This allows users to collect and visualise a Docker hosts activity. 
