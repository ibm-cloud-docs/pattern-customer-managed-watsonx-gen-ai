---
copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai

keywords:
---
{{site.data.keyword.attribute-definition-list}}

# Architecture decisions for storage
{: #storage-arch}

The following table summarizes the storage architecture decisions for the customer managed watsonx gen AI pattern.

| Architecture decision | Requirement |  Option | Decision | Rationale |
| -------------- | -------------- | -------------- | -------------- | -------------- |
| Primary storage for worker nodes | Primary disk used for the worker node operating system  | | 100 GB VPC Block storage | |     
| Secondary storage for worker nodes | Seconary disk used for container runtime needed for large images | - VPC Block storage (5 IOPS) \n - VPC Block storage (10 IOPS) \n | 10 IOPS secondary storage and at least 600 GB (600gb.10iops-tier) | Highly recommended to use the 10-iops tiers or higher for secondary storage since lower tiers can lead to degraded peformance for pulling images or for pods writing to the storage. |
| Containers software defined storage | Provide highly available storage that abstracts data storage for worker nodes and aggregates them into a virtual pool. | - Portworx \n - OpenShift Data Foundation \n  | OpenShift Data Foundation | Highly available storage solution that you can use to manage persistent storage for your containerized apps. |
| Logs storage: Audit and operational  | Provide highly available storage for logs  | - VPC Block storage  \n - Cloud Object Storage  | VPC Block storage  | Built-in Red Hat OpenShift monitoring tools are used to and can be installed by using the cluster logging operator. The cluster logging instance needs an {{site.data.keyword.Bluemix_notm}} Block Storage class. |
{: caption="Architecture decisions for Storage" caption-side="bottom"}
