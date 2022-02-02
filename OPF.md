# 2021 Spring Co-op Project
#### Improvisation of Storage Monitoring in the Operate First Environment 

The [Operate First](https://www.operate-first.cloud/) enviroment is hybrid cloud environment with the purpose of enabling smaller developing projects and research projects to have access to a production level cloud environment.

### What exactly is Operate First?
- Operate First manages OpenShift Clusters
- Uses GitOps workflow to allow quick onboarding for projects(namespaces)
- Allows Data Scientist to focus more on their work, than their enviroment 

| Buzz Words  | Definition |
| ------------- | ------------- |
| MOC  | Mass Open Cloud, Is an environment that consists of two OpenShift clusters, one containing Infra Cluster and the Smaug Cluster  |
| Infra Cluster  | A management cluster, small in size, and houses both ArgoCD and ACM deployments.  |
| Smaug Cluster  | Worker cluster, larger in size, contains user workloads and our own managed deployments (One of which is a Open Data Hub instance) | 
| ArgoCD  | Deploys applications in destinations, and these destiniations are clusters |
| ACM | Advanced Cluster Management, deploys and manages clusters | 
| Prometheus | An open-source monitoring and alert framework that collects metrics via HTTP pull requests| 
| Thanos | An extension of promtehus, which stores metrics at a longer term than Prometheus |
| Loki | A log aggregation system inspired by Prometheus|
| Grafana | Visualization tool used for visualizing metrics and logs, in our instance quired from Prometheus, Thanos, and or Loki|

## Operate First Monitoring Architecture
**TBA**
