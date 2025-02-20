---
copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai

keywords:
---
{{site.data.keyword.attribute-definition-list}}

# Resiliency design


## Cluster availability

By utilizing a multizone clusters for the customer managed watsonx gen ai pattern, the worker nodes are distributed across availability zones that are selected by the user. IBM Cloud automatically provisions three replicas of primary components spread across availability zones within a region for high availability.

It is recommended to spread the worker nodes evenly across three zones, with 50% capacity provisioned in each zone for a total 150% capacity across all worker nodes. This is a cost-efficient solution that guarantees 100% capacity for the workloads if one zone fails and provides 99.99% infrastructure availability. In contrast, spreading the nodes across two zones would require 100% capacity in each zone for a total capacity of 200% vs 150% and would offer only 99.9% infrastructure availability.

Multizone clusters, also known as stretched clusters, provide protection from zone failures and physical host failures. If resources in one zone go down, the workloads can continue to run in worker nodes in the other zones.

## Application availability

By utilizing OpenShift Data Foundation for the pattern, data is replicated to provide persistent storage and ensures the application can be rescheduled to a different worker node if there is a failure without losing data.
