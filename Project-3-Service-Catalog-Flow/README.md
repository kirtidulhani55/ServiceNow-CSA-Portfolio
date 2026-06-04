# Project 3: Service Catalog Automation using Flow Designer (End-to-End Approval Workflow)

## Problem Statement

IT teams manually handle software access requests which can lead to delays, missed approvals, and limited visibility into the approval and fulfillment process.

## Overview

Built an end-to-end ServiceNow Service Catalog solution that automates the full lifecycle of a software access request from submission and manager approval to IT fulfillment and completion notifications using Flow Designer.

## Features

* Built Service Catalog hierarchy:
  Service Catalog → Software Services → Software Access → Software Access Request
* Created a catalog item with 11 variables to capture request details
* Used 3 Variable Sets to organize Employee, Security, and Device information
* Implemented a Manager Approval Required (Yes/No) variable to drive workflow decisions
* Automated approvals, task creation, notifications, and request tracking using Flow Designer
* Handled three request outcomes:

  * No approval required
  * Approved
  * Rejected

## Flow Logic

* RITM is created when the request form is submitted
* Flow checks whether Manager Approval is required

* If Yes:
  * Send approval request to manager
  * If Approved:
    * Create Catalog Task
    * Send notification email
    * Wait for task completion
    * Send final completion email
    * End flow
    
  * If Rejected:
    * Send rejection email
    * End flow
    
* If No:
  * Create Catalog Task
  * Send notification email
  * End flow
  
## Technologies Used

* ServiceNow
* Service Catalog
* Flow Designer
* Catalog Variables
* Variable Sets
* Approval Engine
* Email Notifications
* Catalog Tasks (sc_task)
* Requested Items (RITM)

## Challenge Faced

While testing the solution, approval requests were unexpectedly being routed to Eric Schroeder even though no such approver had been configured in the flow.

### Root Cause

The catalog item price was set to $1,500. ServiceNow includes an out-of-the-box approval rule that automatically generates a Request-level approval when the total request value exceeds $1,000.

This approval was being created independently of the Flow Designer logic.

### Resolution

Reduced the catalog item price from $1,500 to $800, preventing the default Request-level approval from triggering.

### Key Learning

When troubleshooting approval issues in ServiceNow, it is important to investigate platform-level approval rules and out-of-the-box configurations in addition to custom Flow Designer logic.

## What I Learned

* Building Service Catalog solutions from scratch
* Creating and organizing Catalog Variables and Variable Sets
* Designing conditional workflows using Flow Designer
* Implementing manager-based approval processes
* Automating email notifications
* Managing RITM and Catalog Task relationships
* Troubleshooting approval behavior across multiple ServiceNow components

## Result

* Automated software access request lifecycle
* Dynamic manager approval routing
* Automated Catalog Task creation
* Automated requester notifications
* Clean handling of approvals and rejections
* Improved request tracking and fulfillment visibility
* Resolved an unexpected platform-level approval issue 
  that was not covered in any tutorial

## Screenshots
### Catalog Item Configuration
![Catalog Item Configuration](CatLogItem.png)


### Catalog Item :Service Portal View
![Service Catalog Item Form](ScItem.png)
![Service Catalog Item](SCItem.png)

### Variables (11)
<img width="1912" height="595" alt="Screenshot 2026-06-04 201308" src="https://github.com/user-attachments/assets/8272f378-6cab-429a-9dcf-55bfe192c3b6" />

### Variable Sets (3)
<img width="1919" height="865" alt="Screenshot 2026-06-04 201324" src="https://github.com/user-attachments/assets/39627571-807e-4e2e-92e2-ccf50a80f802" />


### Flow Designer
<img width="638" height="924" alt="image" src="https://github.com/user-attachments/assets/d41d9398-eefd-4654-9e6d-71b2a592bc00" />

### Request Submitted , REQ Generated
<img width="1538" height="508" alt="Screenshot 2026-06-04 201129" src="https://github.com/user-attachments/assets/1067ae58-3ac6-407a-95b3-9f652fbb32ae" />


### RITM Record
<img width="1916" height="942" alt="Screenshot 2026-06-04 201217" src="https://github.com/user-attachments/assets/db5e0685-8c3b-4bdf-836d-a03e0161d93e" />


### Approval : Approved Path
<img width="1919" height="488" alt="Screenshot 2026-06-04 201244" src="https://github.com/user-attachments/assets/c1aa6d2f-d030-4770-9395-85618810c445" />


### Catalog Task Closed Complete
<img width="1919" height="924" alt="Screenshot 2026-06-04 201419" src="https://github.com/user-attachments/assets/d189146b-db07-4adf-b9ba-0c6af313924d" />


### Final Email Request Fulfilled
<img width="1066" height="429" alt="Screenshot 2026-06-04 201550" src="https://github.com/user-attachments/assets/527d3591-0757-4f27-9eca-3ff1139dfdf0" />


### Approval : Rejected Path
<img width="1919" height="307" alt="image" src="https://github.com/user-attachments/assets/9ea900ee-4a9d-4e55-a95d-dc6d070776aa" />
<img width="1918" height="753" alt="image" src="https://github.com/user-attachments/assets/b5ba1b4a-bf4e-4d79-80c3-4c6c26e327ba" />


### Rejection Email
<img width="984" height="413" alt="image" src="https://github.com/user-attachments/assets/fffcb960-cec9-4e55-bbab-684c11f85bc2" />




