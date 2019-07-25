# k8s-elasticsearch

[![Build Status](https://travis-ci.org/inhumantsar/ansible-role-k8s-elasticsearch.svg?branch=master)](https://travis-ci.org/inhumantsar/ansible-role-k8s-elasticsearch)

Launches an Elasticsearch cluster into Kubernetes

## Requirements

What does the user need to do ahead of time to ensure this role will work for them?

## Supported Platforms

* RHEL / CentOS: 6, 7      
* Fedora: 24-28      
* Debian:
    - jesse
    - sid
    - stretch
    - buster      
* Ubuntu
    - bionic
    - artful
    - zesty
    - yakkety
    - xenial
* Alpine

## Variables & Defaults

### Storage Class

This role creates a StorageClass for ElasticSearch. If `kses_infra` is set to 'aws' or 'gce', then this is set automatically, otherwise you will havve to set them yourself. 

```
    k8ses_storage_provisioner: kubernetes.io/gce-pd
    k8ses_storage_type: "{{ 'pd-sdd' if not k8ses_storage_type else k8ses_storage_type }}"
```

### oauth2 proxy

if not used to secure kibana, kibana will only be reachable from within the cluster. you'll need a vpn or a bastion host on the appropriate subnets to make that work.

See [`defaults/main.yml`](defaults/main.yml) for more information.

## Usage

Provide an example of the role in action.

## Dependencies

List any other roles which this one depends on and briefly explain why.

## License
[BSD](LICENSE)

## Authors
[Shaun Martin](https://github.com/inhumantsar)