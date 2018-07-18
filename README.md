# Creating A Mutating Admission Webhook

This document walks through the steps required to provide a proxy environmental variables to all workloads in a cluster.
It does this by creating and deploying a [Mutating Admission Webhook](https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/).

## Prerequisites

* Kubernetes Cluster with version > 1.10. (i.e. CFCR >v0.17 or PKS >1.1.1)

## Overview

The Mutating Admission Webhook we will create in this document will automatically edit all pods being applied to the cluster.  It edits the pod by injecting a NO_PROXY environmental variable into all containers.

Our Mutating Admission Webhook is a Kubernetes deployment which will be deployed to your Kubernetes cluster.

The example here is based on the example provided [by Kubernetes](https://github.com/kubernetes/kubernetes/blob/v1.10.5/test/images/webhook/main.go).


