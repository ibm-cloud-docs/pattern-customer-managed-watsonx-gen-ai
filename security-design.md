---
copyright:
  years: 2025
lastupdated: "2025-02-18"

subcollection: pattern-customer-managed-watsonx-gen-ai

keywords:
---
{{site.data.keyword.attribute-definition-list}}

# Security design
{: #security-design}

The following security design decsisons should be considered for the customer managed watsonx Gen AI:

* Use of IBM Cloud IAM roles to the RBACs [for platform and service roles](https://cloud.ibm.com/docs/openshift?topic=openshift-iam-platform-access-roles&interface=ui)
* Separation of environments follows principle of separation of duties and least privilege:
   * Separation of duties - No user should be given enough privileges to misuse the system on their own. No developer access to production.
   * Least privilege - restrict access privileges of authorized personnel to the minimum necessary to perform their jobs.
* Separate account resource groups to isolate production and non-production environments.
* Administrative and operator access goes through a Bastion host.
* VPC Access Control Lists (ACLs) and security groups provide filter and secure traffic to only trusted sources.
* Use of [Secure by Default](/docs/openshift?topic=openshift-vpc-security-group-reference) within Red Hat OpenShift on IBM Cloud whenever possible. 

  Access to outside container registry will be needed for certain Operators. {: note}

* Use of a image registry that is private, highly available, secure and includes vulnerability scanner.
* Use of Key Protect to support data encryption with customer-provided keys to meet regulatory compliance requirements. Key Protect uses a shared FIPS 140-2 level 3 certified hardware security module (HSM) to store keys that are used by storage services for envelope encryption and is also used to offload TLS/SSL keys.
* Data in transit is encrypted using TLS encryption. The Secrets Manager cloud service is used to store and manage secrets and credentials to access applications and cloud resources, as well as SSL/TLS certificates and private keys.
