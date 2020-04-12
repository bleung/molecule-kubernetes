# Molecule-Kubernetes

This repository contains an example ansible role that uses molecule and kubernetes for testing. By default, molecule uses docker containers as a source for containers, which also requires Docker to be installed and running on the server used for testing. 

The purpose of this repository is to demonstrate that testing can also be achieved by using an external kubernetes cluster to host Linux containers for ansible role testing.

## Requirements

A kubernetes server and kubernetes client is required to run this molecule test. The kubernetes deployment won't be covered here, but if an existing remote kubernetes cluster exists, the kubernetes client will still need to be installed on the server running this test.

```
yum install kubernetes-client
```

A kubernetes configuration file will also be required to authenticate against the remote kubernetes cluster and saved at `~/.kube/config`.

The ansible playbooks used across the tests uses the `k8s` module and thus requires the python openshift library

```
pip3 install openshift
```

