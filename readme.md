# elasticsearch

Download - https://www.elastic.co/downloads/elasticsearch

```sh
cd elasticsearch-8.2.2
prateekashtikar@Prateeks-MacBook-Pro elasticsearch-8.2.2 % bin/elasticsearch

ℹ️  Password for the elastic user (reset with `bin/elasticsearch-reset-password -u elastic`):
  Fe*95OGKD+ffNABfOJZy

ℹ️  HTTP CA certificate SHA-256 fingerprint:
  7cbe56915c4f86e307cdea1bd93520edd93ccabc93bf65fcdb1f38c95024ca59

ℹ️  Configure Kibana to use this cluster:
• Run Kibana and click the configuration link in the terminal when Kibana starts.
• Copy the following enrollment token and paste it into Kibana in your browser (valid for the next 30 minutes):
  eyJ2ZXIiOiI4LjIuMiIsImFkciI6WyIxOTIuMTY4LjAuMjo5MjAwIl0sImZnciI6IjdjYmU1NjkxNWM0Zjg2ZTMwN2NkZWExYmQ5MzUyMGVkZDkzY2NhYmM5M2JmNjVmY2RiMWYzOGM5NTAyNGNhNTkiLCJrZXkiOiJPQWo0V0lFQjZkT0lxR3pqN3JTTzo4Z3hBNGlrMVJXQ2RpOEZBbjhzQnJBIn0=

ℹ️  Configure other nodes to join this cluster:
• On this node:
  ⁃ Create an enrollment token with `bin/elasticsearch-create-enrollment-token -s node`.
  ⁃ Uncomment the transport.host setting at the end of config/elasticsearch.yml.
  ⁃ Restart Elasticsearch.
• On other nodes:
  ⁃ Start Elasticsearch with `bin/elasticsearch --enrollment-token <token>`, using the enrollment token that you generated.

```
# Only for MAC

```sh
mv kibana-8.2.2 kibana

cd kibana

xattr -d -r com.apple.quarantine kibana

bin/kibana
```

