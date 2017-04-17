The Prometheus server requires a configuration file that defines the endpoints to scrape along with how frequently the metrics should be accessed.

The first half of the configuration defines the intervals.

<pre class="file" data-filename="prometheus.yml" data-target="replace">
global:
  scrape_interval:     15s
  evaluation_interval: 15s
</pre>

The second half defines the servers and ports that Prometheus should scrap data from. In this example, we have defined three targets running on different ports.

<pre class="file" data-filename="prometheus.yml">
scrape_configs:
  - job_name: 'prometheus'

    static_configs:
      - targets: ['localhost:9090', 'localhost:9100', 'localhost:9323']
        labels:
          group: 'prometheus'
</pre>


_9090_ is Prometheus itself. Prometheus exposes information related to its internal metrics and performance.

_9100_ is the Node Exporter Prometheus process. This exposes information about the Node, such as disk space, memory and CPU usage.

_9323_ is the Docker Metrics port just exposed. This reports information from the Docker Engine.

More information on the default ports can be found at https://github.com/prometheus/prometheus/wiki/Default-port-allocations

Copy the configuration to the editor to continue.
