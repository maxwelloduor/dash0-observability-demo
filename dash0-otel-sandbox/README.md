# Platform Observability with Perses and Dash0

## Quick Start

```bash
./run.sh
```

## Stop

```bash
docker compose down --remove-orphans
```

## Services

- Platform API: http://localhost:8080
- Prometheus: http://localhost:9090  
- Perses: http://localhost:3000
- Jaeger: http://localhost:16686
- OpenSearch Dashboards: http://localhost:5601
- OpenSearch: http://localhost:9200


## Setup Index Pattern for Logs

1.Open OpenSearch Dashboards

2.Go to Discover

3.Create a new Index Pattern eg

```bash
otel-logs-*
```

4.Select @timestamp as the time field

5.Click Create index pattern

You can now view logs ingested from your Platform Service.

