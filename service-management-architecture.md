---
copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai
keywords:
---
{{site.data.keyword.attribute-definition-list}}

# Architecture decisions for service management
{: #service-management-arch}

The following summarize the architecture decisions for service management for customer managed watsonx gen AI pattern.

## Architecture decisions for monitoring
{: #monitoring}

| Architecture decision                                                              | Requirement                                                                                              | Option                                                              | Decision                              | Rationale                                                                                                                                                                                                                                                |
| ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Operational monitoring of cloud infrastructure and services                        | Monitor system health to detect issues that might impact the availability of the system and application. | - IBM Cloud Monitoring \n - Bring Your Own Monitoring Tool                     | IBM Cloud Monitoring                  | IBM Cloud Monitoring collects and monitors operational metrics for cloud infrastructure as well as the cloud platform and services and provides a single view for all metrics                                                                            |
| Operational monitoring of applications                                             | Monitor app health to detect issues that might impact the availability of the app.                       | - IBM Cloud Monitoring \n - Instana (SaaS) \n - IBM Cloud Pak for Data integrated monitoring \n - Bring Your Own Monitoring Tool | IBM Cloud Monitoring + Instana (SaaS) + IBM Cloud Pak for Data integrated monitoring | Instana is used along with IBM Cloud Monitoring to get more application performance metrics and automate Application Performance Management. Instana provides data and actionable insights to monitor the applications and automate root-cause analysis. Information on [IBM Cloud Pak for Data integrated monitoring](https://www.ibm.com/docs/en/software-hub/5.1.x?topic=administering-post-installation-setup-day-1) |
{: caption="Architecture decisions for monitoring" caption-side="bottom"}

## Architecture decisions for logging
{: #logging}

| Architecture decision                                                           | Requirement                                                                                                 | Option                                                                  | Decision                                     | Rationale                                                                                                                                                   |
| ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Log monitoring of cloud infrastructure and services                             | Monitor operational logs to detect issues that might impact the availability of the system and application. | - IBM Cloud Logging \n - Bring Your Own Logging Tool                               | IBM Cloud Logging                            | IBM Cloud Logging collects operational logs from applications, platform resources, and infrastructure and provides interfaces to view and analyze all logs. |
| Log monitoring of IBM Cloud Pak for Data                                                        | Monitor application operational logs to detect issues that might impact the availability of the app.        | - IBM Cloud Logging \n - Application Logging Tool \n - Bring Your Own Logging Tool | IBM Cloud Logging | IBM Cloud Logging collects logs from applications.                              |
{: caption="Architecture decisions for logging" caption-side="bottom"}

## Architecture decisions for auditing
{: #auditing}

| Architecture decision                                                            | Requirement                                                                                    | Option                                                                 | Decision                                        | Rationale                                                                                                                                                                                    |
| -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Audit logging                                                                    | Monitor audit logs to track changes to cloud resources and detect potential security problems. | IBM Cloud Logs \n - Hosted Event Search \n - Event Routing | IBM Cloud Logs \n - Hosted Event Search | IBM Cloud Logs-Hosted Event Search provides interfaces to capture, store, view, search, and monitor user-initiated actions to provision, access, and manage IBM Cloud resources. |
| Application Audit logging                                                                    | Monitor user activity  | IBM Cloud Pak for Data integrated audit logging | IBM Cloud Pak for Data audit logging can be used so you can use this information to identify suspicious activity and block the user from accessing the web client while the activity is investigated. |
{: caption="Architecture decisions for auditing" caption-side="bottom"}

## Architecture decisions for alerting
{: #alerting}

| Architecture decision                                                            | Requirement                                                                                                                           | Option                                                             | Decision                                                           | Rationale                                                                                                                                                                                                                                                                |
| -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Operational alerts                                                               | Provide a mechanism to identify and send notifications about operational issues that are found across application and infrastructure. | IBM Cloud Monitoring, IBM Cloud Logging, and Event notifications    | IBM Cloud Monitoring, IBM Cloud Logging, and Event notifications    | IBM Cloud Monitoring and IBM Cloud Logging support the configuration of alerts to detect operational issues and send notifications to targeted channels. \n Event notifications are used to route the alert events to service destinations to automate response actions. |
| Audit alerts                                                                     | Provide a mechanism to identify and send notifications about issues that are found in audit logs.                                     | IBM Cloud Logs, IBM Monitoring, and Event notifications | IBM Cloud Logs, IBM Monitoring, and Event notifications | IBM Cloud Logs supports the configuration of alerts to detect audit issues and send notifications to targeted channels. \n Event notifications are used to route the alert events to service destinations to automate response actions.                            |                                                                              
{: caption="Architecture decisions for alerting" caption-side="bottom"}
