---
title: Vector Discarded Events
weight: 20
---

# VectorDiscardEvents

## Meaning

Vector discarded events because it was unable to keep up with the rate of incoming events.

## Impact

This means that some events were not processed by Vector. This means that some logs were not sent to Loki, which means that they are not available in Grafana.

## Diagnosis

Check the Vector logs for errors. If there are no errors, check the Vector metrics for the `vector_events_discarded_total` metric. If the metric is increasing, it means that Vector is unable to keep up with the rate of incoming events.
Also check the other metrics on the [vector dashboard](https://jodel.grafana.net/d/29EMYjX7z/overview?orgId=1&var-datasource=grafanacloud-prom&var-cluster=prod-main-new) for irregularities.

## Mitigation

To address this alert, you can either scale up the Vector deployment or reduce the rate of incoming events.
As we deploy Vector as a DaemonSet, scaling up the deployment will scale up Vector on all nodes.
