---
copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai
keywords:
---
{{site.data.keyword.attribute-definition-list}}

# Management and monitoring
{: #management-monitoring}

The recommended approach for multi-cluster management and monitoring is to use IBM Cloud tools that include IBM Cloud Log and IBM Cloud Monitoring. This approach enables application cluster metrics log aggregation and central management within IBM Cloud.

## IBM Cloud Log
{: #log-analysis}

You can use IBM Cloud Log to add log management capabilities to Red Hat OpenShift VPC clusters and provide for the following:

- Customizable user interface for live streaming of log tailing, real-time troubleshooting issue alerts, and log archiving.
- Quick integration with the cluster via a script.
- Aggregated logs across clusters and cloud providers.
- Historical access to logs.
- Highly available, scalable, and compliant with industry security standards.
- Integrated with IBM Cloud IAM for user access management.

## IBM Cloud Monitoring
{: #ibm-cloud-monitoring}

You can use IBM Cloud Monitoring to monitor the performance and overall system health of Red Hat OpenShift VPC clusters and provide for the following:

- Customizable user interface for a unified view of cluster metrics, container security, resource usage, alerts, and custom events.
- Quick integration with the cluster via a script.
- Aggregated metrics and container monitoring across clusters and cloud providers.
- Historical access to metrics that is based on the timeline and plan, and the ability to capture and download trace files.
- Highly available, scalable, and compliant with industry security standards.
- Integrated with IBM Cloud IAM for user access management.

For more information, see [Working with the Red Hat OpenShift agent](/docs/monitoring?topic=monitoring-agent_openshift)

## Flow Logs for VPC clusters
{: #flow-logs}

Configure IBM Cloud Flow Logs for VPC to gather information about the traffic entering or leaving VPC cluster worker nodes. Flow logs are stored in an IBM Cloud Object Storage instance and can be used for troubleshooting purposes, adhering to compliance regulations. For more information, see [Flow logs use cases](/docs/vpc?topic=vpc-flow-logs&interface=ui#flow-logs-use-cases).


## IBM Cloud Pak for Data monitoring
{: #application-monitoring}

IBM Cloud Pak for Data allows the user to monitor the services that are running on the platform, understand how you are using cluster resources, and be aware of issues as they arise.  You can also setup audit events for auditting purposes.  See [Ongoing maintenace (Day 2)](https://www.ibm.com/docs/en/cloud-paks/cp-data/5.0.x?topic=administering-ongoing-maintenance-day-2) for best practices and for monitoring and auditing information.
