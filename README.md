# 2021 Spring Co-op Project
**Title**: Improvisation of Storage Monitoring in the Operate First Environment \
**Co-op**: Bryan Montalvan \
**School**: University of Massachussetts Lowell 

## My Project Proposal
My project for this spring period is to improve the way we currently monitor storage metrics in the [Operate First Enviroment](https://www.operate-first.cloud/). This will be done by creating a grafana dashboard which will store storage data by cluster and its respective namespace.

Whether you are a developer or administrator, having the ability to view how your storage metrics and logs is great asset to understand
the health of your application's deployment. Knowing if your [PV](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) is about to max out on resources is crucial on knowing when to request more storage
or to find out what is using resources on your namespace. 

I also have a complimentary project idea which is to create a `Predictable Consumption Model` witch can predict when a PV will be full. And could
forecast other storage reated metrics/occurences. This idea can potentially involve alerting, more research will be done on this idea down the line.

## How will this be done?
### Storage Dashboard:
First I will check the data we pull from Prometheus checking any labels with `Node` or `Ceph` and get an understanding of what type of metrics
I have to my disposal. Afterwards I'll only take the metrics that users would deem useful, and then starts the research portion.

**When creating data visualization its always important to follow these guidelines**
- Make the metrics/data make sense
- Each time a metric is pulled, it acquires a cost so pull only what you need
- Understand your intended audience

Once I have a starting idea as to what should be visualized I'll use the visulization tool, [Grafana](https://grafana.com/grafana/dashboards/), to create visulizations which drive my projects intentions. Making the users life easier by knowing the state of their project's storage.

**Metrics:**\
`OpenShift -> Prometheus or Thanos -> Grafana`\
**Logs:**\
`OpenShift -> Loki -> Grafana`

### Predictable Consumption Model (PCM):
Creating a Predictable Consumption Model will be the second task of this whole project, with my current vision in my mind.
I will fetch logs from both `Prometheus(for metrics)` and `Loki(for logs)`, to show users when they may be close to running out of storage
and at the same time letting users know if they're requesting too much data(logs).

This complementary idea is in its rough draft phase and will be focused on when the `Storage Dashboard` is closer to completion.

## Note:
If you are unfamilar with Operate First, please take a look at a simple introductary [doc](about-opf.md) to better understand what the initative is and how
the monitor infrastructure works.
