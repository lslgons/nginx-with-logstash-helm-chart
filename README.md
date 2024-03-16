# A Helm chart for nginx with Logstash sidecar
---
For Create Nginx web service on kubernetes, it enables logstash to transfer nginx web log data to elasticsearch.

Just Install by
```bash
helm install your-application ./ -n your-namespace --set logstash.enabled=true
```

