---
copyright:
  years: 2025
lastupdated: "2025-07-21"

subcollection: pattern-customer-managed-watsonx-gen-ai

keywords: watsonx-gen-ai
---
{{site.data.keyword.attribute-definition-list}}

# Deploying the customer-managed watsonx Gen AI pattern

{: #cp4d-overview}

This guide outlines deploying the customer-managed watsonx Gen AI solution onto an {{site.data.keyword.openshiftlong_notm}} cluster. The deployment is based on an existing deployable architecture template.

This deployment utilizes IBM Cloud Pak for Data to install one or more of the following services: watsonx.ai, Watson Assistant, Watson Discovery.

## Before you begin
{: #cp4d-prereqs}

You need the following items to deploy and configure this reference architecture:

* An [IBM Cloud account](https://cloud.ibm.com/registration).
* Required IAM access policies.
* An existing [{{site.data.keyword.openshiftlong_notm}}](/docs/openshift?topic=openshift-getting-started) cluster.
* GPU worker nodes that meet [IBM Cloud Pak for Data requirements](https://www.ibm.com/docs/en/software-hub/5.1.x?topic=requirements-hardware).
* [OpenShift Data Foundation](/docs/openshift?topic=openshift-ocs-storage-prep) installed.
* [OpenShift AI in {{site.data.keyword.openshiftshort}}](/docs/openshift?topic=openshift-ai-addon-about) installed.
* [Cloud Pak for Data entitlement key](https://myibm.ibm.com/products-services/containerlibrary).
  
## Provision Architecture
{: #cp4d-provision}

You can provision the customer-managed watsonx Gen AI pattern via the IBM Cloud catalog.  

1. Access the [watsonx self-managed on Red Hat OpenShift](https://cloud.ibm.com/catalog/7a4d68b4-cf8b-40cd-a3d1-f49aff526eb3/architecture/deploy-arch-ibm-watsonx-self-managed-3b9ffe49-80e7-417b-9179-a2882d3c2517-global) pattern to provision it into your existing Red Hat Openshift Cluster.

## Additonal Services
{: #additonal-cp4d}

You can add additional services onto the watsonx Gen AI pattern.  The addtional services include:

1. [Account Infrastructure base](https://cloud.ibm.com/catalog/7a4d68b4-cf8b-40cd-a3d1-f49aff526eb3/architecture/deploy-arch-ibm-account-infra-base-63641cec-6093-4b4f-b7b0-98d2f4185cd6-global) for creating and configuring the foundational components of an IBM Cloud account
2. [IBM Cloud Observability](https://cloud.ibm.com/catalog/7a4d68b4-cf8b-40cd-a3d1-f49aff526eb3/architecture/deploy-arch-ibm-observability-a3137d28-79e0-479d-8a24-758ebd5a0eab-global) for provisioning and configuring logging, monitoring, and activity tracking.
3. [IBM Cloud Event Notifications](https://cloud.ibm.com/catalog/7a4d68b4-cf8b-40cd-a3d1-f49aff526eb3/architecture/deploy-arch-ibm-event-notifications-c7ac3ee6-4f48-4236-b974-b0cd8c624a46-global) for a high-throughput message bus that is built with Apache Kafka.
4. [Security and Compliance Center](https://cloud.ibm.com/catalog/7a4d68b4-cf8b-40cd-a3d1-f49aff526eb3/architecture/deploy-arch-ibm-scc-9423f9bc-1290-4c71-a9ac-01898bfa7ccc-global) for compliance posture of your deployed resources.
