# 1. Identity and Access Management

- [1. Identity and Access Management](#1-identity-and-access-management)
  - [1.1. Introduction to Identity and Access Management](#11-introduction-to-identity-and-access-management)
  - [1.2. What is Azure Active Directory?](#12-what-is-azure-active-directory)
  - [1.3. What is Role-based Access Control (RBAC)](#13-what-is-role-based-access-control-rbac)
    - [1.3.1. What are Roles?](#131-what-are-roles)
    - [1.3.2. What is Security Principal?](#132-what-is-security-principal)
    - [1.3.3. What is a Scope?](#133-what-is-a-scope)
    - [1.3.4. What is a Role assignment?](#134-what-is-a-role-assignment)
    - [1.3.5. What are Groups?](#135-what-are-groups)
    - [1.3.6. What if there are multiple overlapping role assignments?](#136-what-if-there-are-multiple-overlapping-role-assignments)
    - [1.3.7. Did you think Deny assignments?](#137-did-you-think-deny-assignments)
  - [1.4. What's next](#14-whats-next)

## 1.1. Introduction to Identity and Access Management
In this section, we will take a look at Identity and Access Management (IAM) in Azure. Regardless the nature of your job as a cloud practioner, you will always need to understand how to securely authenticate to cloud resources (i.e., Azure Portal, Azure Subscription, Azure Virtual Machines, etc.). If you are responsible for creating user accounts and granting them access to cloud resources, you will again come across IAM and will need to know how it works so you can properly secure your organization's users and associated resouces.

## 1.2. What is Azure Active Directory?

Azure Active Directory (Azure AD) is Microsoft's cloud-based identity and access management service and it works somewhat similar to Windows Server Active Directory (Windows Server AD), in that it serves a similar function in authenticating users and devices.

Azure AD is used across all the Microsoft online services such as Microsoft 365, Microsoft Dynamics 365, Microsoft Azure, as well as custom applications that software developers may build to run in the Azure cloud. 

When an IT administrator is asked to create a new user account for a new employee, that IT administrator will be using Azure AD to complete this task. Below are some of the additional tasks that can be completed with Azure AD:

* Group creating
* Adding users to a created group
* Multi-Factor Authentication (MFA)
* Device Management
* Hybrid Identity (Sync local Windows Server AD accounts to Azure AD)
* Identity Protection
* Gain insight into signin patterns, and many more

At the end of this section, we will walk through creating a new Azure Active Directoy user account so we can sign in to the Azure Portal.

## 1.3. What is Role-based Access Control (RBAC)

Imagine you have created Azure AD accounts for the users in your organization. This means all your developers, managers, directors, and even third party partners who are helping you to drive digital transformation across your company. How do you decide who gets access to what resources? Before you move forward ensure you understand the difference between [authentication and authorization](https://www.okta.com/identity-101/authentication-vs-authorization/).

Azure RBAC help you to manage who has access to your Azure resources at a very granular level. It is safe to say that Azure RBAC is an authorization system that provides fine-grained access management to Azure resources. For example, with RBAC you can achieve the following example scenarios within your organization:

* Allow a group of users to manage a set of Azure Virtal Machines, while another group of users cannot manage the Virtual Machines
* Allow a user to manage the resource allocation for a database server in Azure, but not be able to stop, or restart the database server
* Allow a user to manage access to an Azure subscription, while other users cannot manage access

These are some simple example, as Azure RBAC afford a great deal of flexibility and power when it comes to managing resources.

### 1.3.1. What are Roles?

A role of role definition is simply a collection of permissions that defines that actions that can be performed and/or not perfomed. For example, a role such as **Reader** allows a security principal (user, group, or application) to have read-only access at the scope at which it was applied. There are many built-in Azure roles and you can even create your own custom roles.

### 1.3.2. What is Security Principal?

A security principal is an object that represents a user, group, or application (service principal or managed identity) that is requesting access to Azure resources. A role is assigned to a security principal.

### 1.3.3. What is a Scope?

A scope the set of resources that the access applies to. For example, when assigning a role to a security principal, you can apply at the scope of a resource, resource group, subscription, or management group. We will look at what these are in the [Azure Hierarcy](../azure-heirarchy/..gitkeep) section. But for now, keep in mind that a scope is used to control the resources to which a security principal has access.

### 1.3.4. What is a Role assignment?

A role assignment is the process of attaching a role to a security principal at a particular scope for the purpose of granting access. Access is granted by creating a role assignment, and that same access can be revoked by removing the role assignment.

### 1.3.5. What are Groups?

A group is a collection of users (or devices). When a role assignment is created with the group as the security principal, the role assignment is transitive. This means if a group is a member of another group that has a role assignment, the user will have the permission in the role assignment.

### 1.3.6. What if there are multiple overlapping role assignments?

Azure RBAC is additive. This means that your effective permissions are the sum of your role assignments.

### 1.3.7. Did you think Deny assignments?

If you were thinking if you can configure a deny assignment, then yes, you can. Deny assignment works very similar to role assignments where a set of deny actions are applied to a security principal.

## 1.4. What's next

[Now that you have completed this section, please move on to the exercises to learn more and gain hands on experience with Azure Active Directory and Role-based Access Control.](../identity-and-access-management/practice/README.md)