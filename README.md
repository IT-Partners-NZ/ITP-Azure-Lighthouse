![IT Partners Limited Logo](img/IT_Partners_Logo.png)

# Introduction

This repository is intended for IT Partners Limited clients to easily and securely provide access to some or all subscriptions in their Azure Tenancy.

The Role base Azure Lighthouse configuration uses Privilaged Groups in IT Partners Limited own Azure Active Directory Tenant.
This provides a mechanism for auditable JIT (Just in Time) privilege access and additional auditibility at no additional cost to the client.

https://docs.microsoft.com/en-us/azure/lighthouse/overview

# What roles get assigned and to who?

## Roles

By renabling Azure Lighthouse access for IT Partners, access will be granted for certain roles to read, modify and create resources on behalf of the client by IT Partners.
More information at Azure AD roles and built-in roles can be found here:
https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles

## IT Partners Groups

IT Partners are using privlege access groups to provide access into your environment. This means no user or admin will have standing access. To gain access IT Partner consultants will need to elevate themselves into the group using Privlege Identity Management within IT Partners own Azure AD Tenant.

This has the benefit of having a full audit trail of who had access and when, additionally it means the licenses required for PIM (Privilaged Access Management) are assigned within IT Partners own Azure AD Tenant and incurs no cost to the Partner.

Additionally when elevating into groups with any kind of write privilege (all except reader) IT Partner consultants will immediately be subject to MFA.

## Role Assignment Summary Table

| **Privileged Access Group**                            | Roles                                    |
| ------------------------------------ | ---------------------------------------- |
| AAD\_ITP-ManagedServices-Contributor | Contributor                              |
| AAD\_ITP-ManagedServices-Contributor | Managed Services Registration assignment |
| AAD\_ITP-ManagedServices-Contributor | Assign roles to Managed Identities       |
| AAD\_ITP-ManagedServices-Reader      | Reader                                   |
| AAD\_ITP-ManagedServices-Operator    | Virtual Machine Contributor              |
| AAD\_ITP-ManagedServices-Operator    | Backup Operator                          |
| AAD\_ITP-ManagedServices-Operator    | Reader                                   |
| AAD\_ITP-ManagedServices-Operator    | Log Analytics Contributor                |
| AAD\_ITP-ManagedServices-Operator    | Monitoring Contributor                   |
| AAD\_ITP-ManagedServices-Operator    | Automation Operator                      |
| AAD\_ITP-ManagedServices-Operator    | Automation Runbook Operator              |
| AAD\_ITP-ManagedServices-Operator    | Managed Application Operator             |
| AAD\_ITP-ManagedServices-Operator    | Site Recovery Operator                   |

# Deploy to Azure

Name | Description   | Auto-deploy   | IT Partners Azure Managed Services |
-----| ------------- |--------------- |-------
| Azure Lighthouse - IT Partners - Subscription Discovery | Grant Read Only access to Microsoft Azure Subscription for IT Partners for Discovery | [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https://raw.githubusercontent.com/IT-Partners-NZ/ITP-Azure-Lighthouse/main/Client-OnboardITPLighthouse.json?token=GHSAT0AAAAAABQD2424KGGK6ORRBMOMS74EYPYK4BQ) | [Managed IT](https://www.itpartners.co.nz/managed-it-services/#managed-it)
| Azure Lighthouse - IT Partners - Subscription Onboard |Onboard your Subscription under IT Partners | [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https://raw.githubusercontent.com/IT-Partners-NZ/ITP-Azure-Lighthouse/main/Client-OnboardITPLighthouse.json?token=GHSAT0AAAAAABQD2424KGGK6ORRBMOMS74EYPYK4BQ) | [Managed IT](https://www.itpartners.co.nz/managed-it-services/#managed-it)

# Remove Access

As a client and owner of your own Azure subscription, access can be removed at any time from the Microsoft Azure Portal. 

To remove from Access from the portal use the search bar to find "Service Providers"

Under Delegations simply select and and **Delete**

To also clean up the left over "Offers" goto the **Service Provider offers** section. Again select all offers and click the **Delete** button.

Remember, removing IT Partners Limited from accessing your Microsoft Azure ecosystem, through the Azure Lighthouse system will mean that the Microsoft Azure environment can no longer be maintaned and monitored by IT Partners Limited.
