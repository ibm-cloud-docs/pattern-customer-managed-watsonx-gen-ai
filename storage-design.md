---
copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai

keywords:
---
{{site.data.keyword.attribute-definition-list}}

# Storage design
{: #storage-design}

The following provides an in-depth view of the different storage types and solutions that are needed for the customer managed watsonx gen AI pattern {{site.data.keyword.redhat_openshift_notm}} pattern.

## Storage types
{: #storage-types}

### Local storage for container images
{: #local-storage}

#### IBM Cloud Block Storage
{: #block-storage-types}

IBM Cloud Block Storage on Kubernetes offers persistent storage for containerized applications, ensuring data durability and scalability. It seamlessly integrates with Kubernetes clusters, providing dynamic provisioning, snapshots, and encryption. This enables efficient management and utilization of storage resources within the Kubernetes environment, enhancing application performance and reliability. For more information, see [Block Storage for VPC documentation](/docs/openshift?topic=openshift-vpc-block).  A minimum of 500 GB of storage space per node will be needed for the containizered application.

### Persistent storage
{: #persistent-storage}

### Portworx
{: #portworx-types}

Portworx is a software-defined storage (SDS) solution that transforms commodity hardware into a robust storage cluster. Portworx provides a high available software-defined storage solution to be used for the local persistent storage for the containerized stateful application across multiple zones for this solution. 

For more information, see [About Portworx](/docs/openshift?topic=openshift-storage_portworx_about){: external}.

### Red Hat OpenShift Data Foundation
{: #openshift-types}

OpenShift Data Foundation is a highly available storage solution that consists of several open source operators and technologies like [Ceph](https://docs.ceph.com/en/latest/dev/developer_guide/intro/){: external}, [NooBaa](https://www.noobaa.io/){: external}, and [Rook](https://rook.io/){: external}. These operators allow you to provision and manage File, Block, and Object storage for your containerized workloads in {{site.data.keyword.openshiftlong}} clusters. OpenShift Data Foundation was selected for this pattern due to its deployment and integration within IBM Cloud Red Hat OpenShift.
