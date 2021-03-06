# Kubernetes The Hard Way Baremetal

This tutorial will walk you through setting up Kubernetes the hard way. This guide is not for people looking for a fully automated command to bring up a Kubernetes cluster. If that's you then check out [Google Container Engine](https://cloud.google.com/container-engine), or the [Getting Started Guides](http://kubernetes.io/docs/getting-started-guides/).

It has been forked from Kelsey Hightower's [Kubernetes The Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way), but uses baremetal rather than AWS or GCE

This tutorial is optimized for learning, which means taking the long route to help people understand each task required to bootstrap a Kubernetes cluster. 

> The results of this tutorial should not be viewed as production ready, and may receive limited support from the community, but don't let that prevent you from learning!

## Target Audience

The target audience for this tutorial is someone planning to support a production Kubernetes cluster and wants to understand how everything fits together. After completing this tutorial I encourage you to automate away the manual steps presented in this guide.

* This tutorial is for educational purposes only. There is much more configuration required for a production ready cluster.

## Cluster Details

* Kubernetes 1.5.1
* Docker 1.12.1
* etcd 3.0.10
* [CNI Based Networking](https://github.com/containernetworking/cni)
* Secure communication between all components (etcd, control plane, workers)
* Default Service Account and Secrets


### What's Missing

The resulting cluster will be missing the following items:

* [Cluster add-ons](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons)
* [Logging](http://kubernetes.io/docs/user-guide/logging)
* [No Cloud Provider Integration](http://kubernetes.io/docs/getting-started-guides/)


## Platforms

This should be virtually agnostic in terms of baremetal, however this tutorial is based on [Vultr](https://www.vultr.com). As we are using Ubuntu, it should work on any provider, such as [Digital Ocean](https://www.digitalocean.com/) or [Linode](https://www.linode.com/)

This tutorial assumes you have access to one of the following:

## Labs

While GCP or AWS will be used for basic infrastructure needs, the things learned in this tutorial apply to every platform.

* [Cloud Infrastructure Provisioning](docs/01-infrastructure.md)
* [Setting up a CA and TLS Cert Generation](docs/02-certificate-authority.md)
* [Bootstrapping an H/A etcd cluster](docs/03-etcd.md)
* [Bootstrapping an H/A Kubernetes Control Plane](docs/04-kubernetes-controller.md)
* [Bootstrapping Kubernetes Workers](docs/05-kubernetes-worker.md)
* [Configuring the Kubernetes Client - Remote Access](docs/06-kubectl.md)
* [Managing the Container Network Routes](docs/07-network.md)
* [Deploying the Cluster DNS Add-on](docs/08-dns-addon.md)
* [Smoke Test](docs/09-smoke-test.md)
* [Cleaning Up](docs/10-cleanup.md)
