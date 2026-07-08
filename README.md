# Automated Network Request Management

## Project Overview

The Automated Network Request Management application is a ServiceNow-based solution developed to automate the complete
lifecycle of network service requests. The application enables users to submit network requests through the Service Catalog, 
automatically routes requests for approvals, creates network task records, updates request status, and sends email notifications 
throughout the process.

This project eliminates manual intervention, improves request tracking, and streamlines network request fulfillment.
# Automated Network Request Management

An end-to-end ServiceNow workflow automation project that streamlines network service request handling using Service Catalog, Flow Designer, approvals, notifications, and custom tables.

## Table of Contents

- Project Overview
- Features
- Architecture
- Technologies Used
- Custom Tables
- Service Catalog
- Workflow
- Email Notifications
- UI Policies
- Auto-Population
- Future Enhancements
- Author
## Architecture

User
   │
   ▼
Service Catalog
   │
   ▼
Flow Designer
   │
   ├── Create Network Database Record
   │
   ├── Send Submission Email
   │
   ├── Request Approval
   │
   ├── If Approved
   │      │
   │      ├── Update Database
   │      ├── Create Network Task
   │      ├── Ask Task Approval
   │      │
   │      ├── If Approved
   │      │      ├── Update Task
   │      │      ├── Update Database
   │      │      └── Completion Email
   │      │
   │      └── If Rejected
   │             ├── Update Task
   │             ├── Update Database
   │             └── Rejection Email
   │
   └── If Initial Request Rejected
          ├── Update Database
          └── Rejection Email

## Features

- Service Catalog based Network Request submission
- Auto-population of requester details using Catalog Client Script and Script Include
- Dynamic Catalog UI Policies
- Automatic creation of Network Database records
- Email notification after request submission
- Manager/Admin approval workflow
- Automatic creation of Network Task after approval
- Network Task approval workflow
- Automatic status updates
- Email notifications for approvals and rejections
- Separate handling for Approved and Rejected requests
- End-to-end automated workflow using Flow Designer

---

## Technologies Used

- ServiceNow
- Flow Designer
- Workflow Studio
- Service Catalog
- Catalog Client Scripts
- Script Includes
- Catalog UI Policies
- GlideAjax
- Notifications (Send Email)
- Custom Tables

---

## Custom Tables

### Network Database

Stores all submitted network requests.

Fields include:

- Request Number
- Requested For
- Customer Address
- Device Type
- Device Details
- Assignment Group
- Assigned To
- Work Status
- Customer Document
- Date of Enquiry

---

### Network Task

Stores network implementation tasks created after request approval.

Fields include:

- Task Number
- Database Number
- Request Number
- Assigned To
- Requested For
- Approval Status
- Work Status
- Description
- Work Notes

---

## Service Catalog Item

**Catalog Item Name**

Network Request

Users submit requests through the Service Portal by providing:

- Requester Information
- Network Service Type
- Address
- Device Type
- Device Details
- Additional Information
- Supporting Documents

---

## Automation Workflow

### Step 1

User submits a Network Request from the Service Catalog.

↓

### Step 2

Requester details are automatically populated.

↓

### Step 3

Flow Designer creates a Network Database record.

↓

### Step 4

Confirmation email is sent.

↓

### Step 5

Approval request is generated.

---

## If Request is Approved

- Update Network Database
- Create Network Task
- Send Task Notification
- Request Network Task Approval

### If Network Task is Approved

- Update Network Task Status
- Update Network Database Status
- Send Completion Email
- End Flow

### If Network Task is Rejected

- Update Network Task Status
- Update Network Database Status
- Send Rejection Email
- End Flow

---

## If Initial Request is Rejected

- Update Network Database Status
- Send Rejection Email
- End Flow

---

## Auto-Population

Requester information is automatically fetched using:

- Catalog Client Script
- GlideAjax
- Script Include

Fields populated include:

- Name
- Email
- Phone Number

---

## UI Policies

Dynamic UI behavior includes:

- Showing Device Details only when "Others" is selected.
- Mandatory fields based on request type.

---

## Email Notifications

Automatic notifications are sent for:

- Request Submitted
- Request Approved
- Request Rejected
- Network Task Created
- Network Task Approved
- Network Task Rejected
- Request Completed

---

## Flow Components

- Service Catalog Trigger
- Get Catalog Variables
- Create Network Database Record
- Send Email
- Ask for Approval
- If Approved Logic
- Update Network Database
- Create Network Task
- Ask Network Task Approval
- If Network Task Approved
- Update Records
- Completion Email
- Rejection Flow
- End Flow

---

## Benefits

- Eliminates manual request processing
- Reduces approval delays
- Improves request visibility
- Centralized tracking of network requests
- Automated notifications
- End-to-end workflow automation
- Better operational efficiency

---

## Future Enhancements

- SLA Management
- Escalation Notifications
- Dashboard & Reports
- Manager-based Dynamic Approvals
- Service Level Monitoring
- Integration with CMDB
- Mobile Support
- Attachment Validation
- Audit Logs
- Analytics Dashboard

---

## Author

**Sandeepthi Sagirisetty**

B.Tech Data Science

ServiceNow Certified System Administrator (CSA)

ServiceNow Certified Application Developer (CAD)

---

## Project Status

Completed

End-to-End Automated Network Request Management Solution using ServiceNow Flow Designe

