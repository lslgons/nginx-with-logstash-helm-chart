# A Helm chart for nginx with Logstash sidecar
---

For Creating Nginx web service on kubernetes, it enables logstash to transfer nginx web log data to elasticsearch.

Just be able to Install by
```bash
helm install your-application ./ -n your-namespace --set logstash.enabled=true
```

## Elasticsearch Self-signed CA
If you have elasticseach on kubernetes, Get CA Certification and write in values.yaml (logstash.esCert.caData)
```
kubectl get secret elasticsearch-master-certs -n your-namespace -o jsonpath="{.data.ca\.crt}" | base64 --decode
```

default caData value is dummy trimmed data, you have to change this value for absolutely running.

## Logs Path
Nginx Logs in Logstash container's is on "/opt/logs", There is no pipeline (just default pipelines)
