# Description
Monitoring Logging fluent-bit Kubernetes to ELK

# How to User
- please install kubectl in laptop or server
- clone repo : git clone git@github.com:peppiii/fluent-bit.git
- use to folder cd fluent-bit
- please read Noted in Readme before execute fluent-bit

# Configmap
- namespaces : logging
- FLUENT_ELASTICSEARCH_HOST : ip elasticsearh
- FLUENT_ELASTICSEARCH_PORT : port elasticsearch
- FLUENT_ELASTICSEARCH_SCHEME : schema by default http
- FLUENT_ELASTICSEARCH_LOGSTASH_PREFIX : index_pattern in elasticsearch ( example: example )
- FLUENT_ELASTICSEARCH_LOGSTASH_INDEX_NAME : index_pattern in elasticsearch (  example: example ))

# Secret
- FLUENT_ELASTICSEARCH_USER : elastic
- FLUENT_ELASTICSEARCH_PASSWORD : please check in elasticsearch

# How To Secret
*  To create the Secret containing the FLUENT_ELASTICSEARCH_USER, choose a user and convert it to base64:
```
$ echo -n 'KubernetesRocks!' | base64
S3ViZXJuZXRlc1JvY2tzIQ==
```
*  To create the Secret containing the FLUENT_ELASTICSEARCH_PASSWORD, choose a password and convert it to base64:
``` 
$ echo -n 'apajaboleh!' | base64
S3ViZXJuZXRlc1JvY2tzIQ==
```
*  please insert to fluent-bit-secret.yml 


# Step Apply
- kubectl apply -f fluent-acl.yml
- kubectl apply -f fluent-bit-configmap.yml
- kubectl apply -f fluent-bit-secret.yml
- kubectl apply -f fluent-bit-daemonset.yml

# License
Commercial use