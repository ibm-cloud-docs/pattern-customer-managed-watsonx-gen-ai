---
copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai

keywords:
---
{{site.data.keyword.attribute-definition-list}}

# Architecture descisions for resiliency
{: #resiliency-architecture}

The following are resiliency architecture decisions for the customer managed watsonx Gen AI pattern.

| Architecture decision | Requirement | Alternative  | Decision | Rationale   |
| --------------------- | ----------- | ------------ | -------- | ----------- |
| High availability               | * Ensure availability of resources if there's an outages. Support Service Level Agreement (SLA) targets for application availability | * [Single-zone cluster](docs/openshift?topic=openshift-strategy)\n * [Multi-zone cluster](docs/openshift?topic=openshift-strategy) \n * [Multiple single-zone clusters in one region](docs/openshift?topic=openshift-strategy) | * Multizone clusters: 3 availability zones | * Built-in high availability that uses three availability zones within a region protects against zone failures. \n * Minimum of 2 worker nodes on each zone for a total of 6 worker nodes is required to meet IBM Cloud 99.99% SLA. \n *  Each zone configured with 50% of required CPU capacity to provide 100% capacity if there's a zone failure. |
{: caption="Architecture decisions for resiliency" caption-side="bottom"}
