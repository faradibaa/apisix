# For Multi-Instance APISIX
In one `docker-compose.yaml` file, there are 3 APISIX and 3 APISIX Dashboard instances.
The one that contains "v3" means it uses version 3 of APISIX or APISIX Dashboard.
Each pair of APISIX & APISIX Dashboard use one ETCD cluster (please check this repo for ETCD configuration: https://github.com/faradibaa/etcd/tree/main/multi-cluster).

## Pre-Setup
Create empty files for logs:
- `dashboard1.log`
- `dashboard2.log`
- `dashboard-v3.log`

## APISIX Configuration
### General
Don't forget to add ETCD IP or hostname.
### Version 2
Using the `apisix.yaml` file, create 2 files:
- `apisix1.yaml`: Use port 9090 & 9180; use ETCD "CLUSTER 1"
- `apisix2.yaml`: Use port 9091 & 9181; use ETCD "CLUSTER 2"
### Version 3
Use `apisix-v3.yaml` file for 3rd APISIX instance.

## APISIX Dashboard Configuration
Using the `dashboard.yaml` file, create 3 files:
- `dashboard-conf1.yaml`: Use port 9000; use ETCD "CLUSTER 1"
- `dashboard-conf2.yaml`: Use port 9001; use ETCD "CLUSTER 2"
- `dashboard-conf-v3.yaml`: Use port 9002; use ETCD "CLUSTER 3"
