---

copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai

keywords: watsonx-gen-ai

---

{{site.data.keyword.attribute-definition-list}}

# Architecture decisions for compute
{: #compute-architecture}

The following table summarizes the compute architecture decisions for the customer managed watsonx gen AI pattern.

| Architecture decision| Requirement | Option | Decision| Rationale|
|---|---|---|---|---|
| Red Hat OpenShift on Virtual Private Cloud (VPC) worker nodes | Provide properly isolated compute resources with adequate compute capacity and storage for the enterprise stateful applications. | - VPC VSIs  \n - VPC Dedicated Hosts  \n -  VPC Bare Metal  \n - VPC Bare Metal Software Defined Storage Compliant | VPC VSIs | The option that is available for Red Hat OpenShift |
| Host profile for worker nodes |    | GPU | Based on gpus, memory, cores, and storage requirements | Select the VSI outlined in the application requirements. A minimum requirement of 48 cores and 240 GB memory and 2 GPU's (gx3.48x240.2l40s) for minimal install of IBM Cloud Pak for Data and OpenShift Data Foundation. See [IBM Cloud Pak for Data Hardware requirements](https://www.ibm.com/docs/en/software-hub/5.1.x?topic=requirements-x86-64-hardware) for additional information. |
| Worker nodes distribution across availability zones |  |  Distribute evenly across three availability zones. | Distribute evenly across three availability zones | If the worker nodes are not spread evenly across the zones or capacity is insufficient in one of the zones, the Red Hat OpenShift controller might fail to schedule all requested pods. |
{: caption="Architecture decisions for compute" caption-side="bottom"}
