# Project 1: Incident Auto-Assignment System (ServiceNow)

## Problem Statement

In many organizations, service desk agents manually assign incidents to the appropriate support groups. This process is time-consuming, prone to human error, and can delay incident resolution.

This project automates incident assignment based on the selected **Service Category** using two different ServiceNow automation techniques: **Assignment Rules** and **Business Rules**.

---

# Project Overview

The objective of this project is to automatically assign incidents to the appropriate Assignment Group based on the selected Service Category.

Two different implementations were developed:

- **Assignment Rule** – Uses ServiceNow's built-in assignment engine for automatic assignment during incident creation.
- **Business Rule** – Uses server-side JavaScript to assign and dynamically reassign incidents whenever the Service Category changes.

---

# Features

- Created a custom **Service Category** field
- Added Service Category choices:
  - Network
  - Software
  - Hardware
  - Access
- Created Assignment Groups for each category
- Automated incident routing
- Implemented both Assignment Rules and Business Rules

---

# Service Category Mapping

| Service Category | Assignment Group |
|-----------------|------------------|
| Network | Network Team |
| Software | Software Team |
| Hardware | Hardware Team |
| Access | Access Management Team |

---

# 1. Assignment Rule Implementation

## 1.1 Configuration

The Assignment Rule evaluates the selected **Service Category** when a new incident is created and automatically assigns the corresponding Assignment Group.

### Screenshot

![Assignment Rule Configuration](https://github.com/kirtidulhani55/ServiceNow-CSA-Portfolio/blob/main/Project-1-Auto-Assignment/AssignmentRule.png?raw=true)

---

## 1.2 Test Result

The incident was automatically assigned to the correct Assignment Group during creation.

![Assignment Rule Test Result](https://github.com/kirtidulhani55/ServiceNow-CSA-Portfolio/blob/main/Project-1-Auto-Assignment/ResultAR.png?raw=true)

---

# 2. Business Rule Implementation

## 2.1 Configuration

The Business Rule executes on **Insert** and **Update**. It checks the selected Service Category and automatically updates the Assignment Group.

### Screenshot

![Business Rule Configuration](https://github.com/kirtidulhani55/ServiceNow-CSA-Portfolio/blob/main/Project-1-Auto-Assignment/Screenshot%202026-05-26%20144420.png?raw=true)

---

## 2.2 Test Result

The Assignment Group is updated automatically whenever the Service Category changes.

![Business Rule Test Result](https://github.com/kirtidulhani55/ServiceNow-CSA-Portfolio/blob/main/Project-1-Auto-Assignment/Screenshot%202026-05-26%20144433.png?raw=true)

---

# Additional Screenshots

## Service Category

![Service Category](https://github.com/kirtidulhani55/ServiceNow-CSA-Portfolio/blob/main/Project-1-Auto-Assignment/Screenshot%202026-05-26%20144227.png?raw=true)

## Assignment Groups

![Assignment Groups](https://github.com/kirtidulhani55/ServiceNow-CSA-Portfolio/blob/main/Project-1-Auto-Assignment/Screenshot%202026-05-26%20144330.png?raw=true)

---

# Results

- Successfully automated incident assignment based on the selected Service Category.
- Eliminated manual assignment of incidents.
- Assignment Rule automatically routes incidents during creation.
- Business Rule supports automatic reassignment when the Service Category changes.
- Improved consistency and reduced manual effort.

---

# Business Rule vs Assignment Rule

| Business Rule | Assignment Rule |
|---------------|-----------------|
| Executes on Insert and Update | Executes during record creation |
| Uses server-side JavaScript | Uses ServiceNow Assignment Engine |
| Supports reassignment | Best for initial assignment |
| Highly customizable | Configuration-based |

---

# Technologies Used

- ServiceNow
- Incident Management
- Business Rules
- Assignment Rules
- Server-side JavaScript
- Assignment Groups

---

# What I Learned

- Creating custom fields and choice lists
- Configuring Assignment Groups
- Implementing Business Rules using server-side JavaScript
- Configuring Assignment Rules
- Understanding the differences between Business Rules and Assignment Rules
- Choosing the appropriate automation technique based on business requirements
