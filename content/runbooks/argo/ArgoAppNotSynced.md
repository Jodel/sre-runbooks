---
title: Argo App Not Synced
weight: 20
---

# ArgoAppNotSynced

## Meaning

At least one Application in Argo CD is not in sync, meaning there is a difference between the state running in Kubernetes and the latest state in git.

## Impact

It's possible that a change was supposed to be deployed, but it was not. In what ways this can impact the system depends on the change itself.

## Diagnosis

Check the application's diff in Argo CD. The diff will show the differences between the state in git and the state in Kubernetes.

## Mitigation

To address this alert, you can either sync the application in Argo CD or revert the change in git.
Make sure to check the diff before syncing or reverting, and consider talking to the person who made the change.
