# Incident Auto-Assignment System (ServiceNow)

## Problem Statement
Service desk teams waste time manually assigning 
incidents to the correct team. This causes delays 
in response time and human errors in routing.

## Overview
Created a ServiceNow automation project that automatically assigns incidents to the correct support group based on the selected Service Category.

## Features
- Added custom field: `Service Category`
- Created choice options:
  - Network
  - Software
  - Hardware
  - Access
- Created assignment groups for each category
- Implemented Business Rule for auto-assignment

## Business Rule Logic
When an incident is created:
- The script checks the selected Service Category
- Based on the category, the Assignment Group is populated automatically

Example:
- Network → Network Team
- Software → Software Team

## Technologies Used
- ServiceNow
- Incident Table
- Business Rules
- Server-side JavaScript
- Form Builder
- Assignment Groups

## What I Learned
- Creating custom fields and choice lists
- Working with Assignment Groups
- Writing basic Business Rule scripts
- Using `current` object in ServiceNow
- Automating ticket routing process

## Screenshots
- Incident form with Service Category
- Assignment Groups
- Business Rule configuration
- Auto-assignment test results

## Result
- Incident INC0010014 successfully auto-assigned 
  to Network Team
- Zero manual intervention required
- Business Rule fires on both Insert and Update
