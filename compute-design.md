---

copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai

keywords: watsonx-gen-ai

---

{{site.data.keyword.attribute-definition-list}}

# Compute design
{: #compute-design-considerations}

The following are the compute design considerations for the customer managed watsonx Gen AI pattern {{site.data.keyword.redhat_openshift_notm}} pattern.

1. A VPC Landing Zone is deployed which provides the ability to automate the installation of an Red Hat OpenShift cluster into a multizone region.
2. The worker pool node size and quantity are determined based on the resource requirements for the application and storage workloads.
3. To meet the Red Hat OpenShift on VPC service availability Service Level Agreement (SLA) of 99.99%, a minimum of 3 worker nodes are equally distributed across three availability zones.
4. By default, the cluster is provisioned with a VPC security group and a cluster-level security group.
5. The Red Hat OpenShift platform is integrated with {{site.data.keyword.Bluemix_notm}}. Services to provide centralized cluster observability services.

## Cloud Pak for Data platform compute requirements
{: #sizing-your-environment}

The size of your cluster depends on multiple factors.

- The shared components that you need to install.
- The services that you plan to install.
- The sizing requirements for services are available in Services.
- The types of workloads that you plan to run.

Please reference the [IBM Cloud Pak for Data Hardware requirements](https://www.ibm.com/docs/en/cloud-paks/cp-data/5.0.x?topic=requirements-hardware#hardware-reqs__platform) for more information on sizing the compute for your cluster.

### Example sizing use-case

For a minimal hardware requirement that supports the install of IBM Cloud Pak for Data, OpenShift Data Foundation and operators, watsonx.ai sw and included required service to support foundation models and prompt tuning, use of the compute profile **gx3.48x240.2l40s** for a 3 zone VPC with 1 worker node per zone can be used.
