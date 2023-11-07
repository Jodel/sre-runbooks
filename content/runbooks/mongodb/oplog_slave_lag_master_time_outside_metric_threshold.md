---
title: Oplog Slave Lag Master Time exceeded threshold
weight: 20
---

# Oplog Slave Lag Master Time exceeded threshold

## Meaning

The replication lag of a secondary is above the alert threshold. This means the secondary couldn't keep up with the number of writes happening in the cluster.

## Impact

Users may not see recent content, e.g. just created comments seem to appear and disappear between refreshes.

## Diagnosis


This alert is often caused by a high number of writes.

Check Atlas cluster metrics (inspect the replication lag metric for the "secondaries")



## Mitigation

Identify any unusual processes (e.g. cronjobs, manual processes) and try to pause/stop them.
