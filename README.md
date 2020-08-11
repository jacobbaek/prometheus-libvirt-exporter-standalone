# prometheus-libvirt-exporter-standalone
libvirt-export that will gather the metric for libvirtd.
This exporter will run as docker container.
This should run on KVM server that is running libvirtd.

# Component
* docker-compose script for prometheus-libvirt-exporter (./docker-compose.yaml)
* grafana dashboard (./grafana-dashboard/)

# Get started
### Docker-compose 

**prometheus-libvirt-exporter installation**
```
# clone the source codes
docker-compose up
```

**prometheus example configuration**
> The Prometheus is running via prometheus-operator.

```     
# sample
    additionalScrapeConfigs:
     - job_name: libvirt-exporter
       scrape_interval: 60s
       static_configs:
       - targets: ['10.10.10.10:9177']

```

### grafana dashboard 
- Libvirt Dashboard.json

These dashboard json file can be imported on Grafana.

> **NOTE**
If you need the libvirtd monitoring that is running on kubernetes,
You can use 'https://github.com/ycy1766/prometheus-libvirt-exporter' helm charts. 
