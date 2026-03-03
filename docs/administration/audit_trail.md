---
title: Audit Trail
description: View, search, and filter system activity logs and audit events
tags:
  - Audit
  - Logs
  - Security
  - Compliance
---

Track and monitor all system activities, user actions, and resource changes through comprehensive audit logs.

---

## Overview

The Audit Trail provides a complete record of all activities within your Buzz HPC account, including resource creation, modifications, deletions, and access events.

---

## Accessing Audit Trail

Navigate to **Administration > Audit Trail** in the left menu.

![Audit Trail](img/administration/audit_trail.png)

---

## Audit Log Table

The audit log displays the following information:

| Column | Description |
|--------|-------------|
| **Timestamp** | Date and time of the event |
| **User** | User who performed the action |
| **Action** | Type of operation (Create, Update, Delete, Access) |
| **Resource Type** | Category of resource affected |
| **Resource Name** | Specific resource identifier |
| **Status** | Success or Failure |
| **IP Address** | Source IP of the request |
| **Details** | Additional event information |

---

## Search and Filter

### Search Functionality

Use the search bar to find specific events:
- Search by user name
- Search by resource name
- Search by action type
- Search by IP address

### Filter Options

Apply filters to narrow down results:

- **Date Range**: Filter by specific time periods
- **User**: Show events from specific users
- **Action Type**: Filter by operation (Create, Update, Delete, etc.)
- **Resource Type**: Filter by resource category (GPU VM, LLM Inference, etc.)
- **Status**: Show only successful or failed operations

![Filter Logs](img/administration/audit_filter.png)

---

## Common Use Cases

### Security Auditing

- Review unauthorized access attempts
- Track user activity patterns
- Identify suspicious behavior
- Monitor privilege escalations

### Compliance

- Generate activity reports
- Track data access
- Document change history
- Audit resource usage

### Troubleshooting

- Investigate failed operations
- Review configuration changes
- Track resource lifecycle
- Debug deployment issues

---

## Export Audit Logs

Export audit logs for archival or external analysis:

1. Apply desired filters
2. Click **Export** button
3. Select format (CSV, JSON)
4. Download file

---

## Retention

Audit logs are retained for 90 days by default. Contact support for extended retention requirements.

---
