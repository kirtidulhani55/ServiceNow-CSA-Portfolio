# Project 2: Role-Based Access Control (RBAC)

## Problem

All users had the same level of access to Incident records, creating a security risk.

## Solution

Implemented Role-Based Access Control (RBAC) using ServiceNow Roles and Access Control Lists (ACLs).

## Roles Used

1. **service_desk_role** - Read access to incidents
2. **approver_role** - Read and write access to incidents
3. **manager_role** - Read and write access based on role requirements
4. **admin_role** - Full system access

## ACLs Configured

1. Incident - Read ACL
2. Incident - Write ACL
3. Role-based access conditions
4. Admin override permissions

## How It Works

* Access is controlled through assigned roles.
* ACLs determine which users can read or modify Incident records.
* Different user groups receive different levels of access.

## Security Benefits

✅ Least Privilege Access

✅ Improved Data Security

✅ Controlled Record Visibility

✅ Role-Based Permissions

## Technologies Used

* ServiceNow Roles
* Access Control Lists (ACLs)
* Incident Management
* Role-Based Access Control (RBAC)

## What I Learned

* Creating and assigning roles
* Configuring ACLs
* Controlling table-level access
* Implementing security best practices in ServiceNow
