# A Helm chart for nginx with Logstash sidecar
---

For Create Nginx web service on kubernetes, it enables logstash to transfer nginx web log data to elasticsearch.

Just Install by
```bash
helm install your-application ./ -n your-namespace --set logstash.enabled=true
```

## Elasticsearch Self-signed CA
If you have elasticseach on kubernetes, Get CA Certification and write in values.yaml (logstash.esCert.caData)
```
kubectl get secret elasticsearch-master-certs -n your-namespace -o jsonpath="{.data.ca\.crt}" | base64 --decode
```

## Logs Path
Nginx Logs in Logstash container's is on "/opt/logs", There is no pipeline (just default pipelines)
