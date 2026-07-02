# Workflow Overview

This project is composed of multiple n8n workflows, each responsible for a specific stage of the AI-powered sales automation pipeline. The workflows are grouped into two logical areas:

- Business Development
- Account Executive

---

# Business Development

The Business Development workflows automate outbound prospecting, CRM management, and personalized outreach generation.

## Business Development Manager

**Purpose**

Acts as the orchestrator for the outbound sales pipeline.

**Responsibilities**

- Receives the Ideal Customer Profile (ICP)
- Coordinates the complete prospecting process
- Invokes the Prospecting, RevOps, and SDR workflows
- Passes data between workflows
- Returns the overall execution summary

---

## Prospecting Sub-Agent

**Purpose**

Identifies companies and decision-makers that match the provided Ideal Customer Profile.

**Responsibilities**

- Searches public sources for potential prospects
- Identifies relevant decision makers
- Collects company and contact information
- Returns structured prospect data

**Output**

- Person name
- Job title
- Company
- Email address

---

## RevOps Sub-Agent

**Purpose**

Synchronizes qualified prospects with the CRM.

**Responsibilities**

- Checks whether the contact already exists
- Creates new contacts when necessary
- Updates existing CRM records
- Prevents duplicate entries

**External Service**

- Pipedrive CRM

---

## SDR Sub-Agent

**Purpose**

Generates personalized outreach emails for qualified prospects.

**Responsibilities**

- Creates tailored outreach messages
- Generates Gmail draft emails
- Personalizes content using prospect information
- Prepares emails for manual review before sending

**External Service**

- Gmail

---

# Account Executive

The Account Executive workflows handle inbound phone calls from prospects responding to outreach campaigns.

---

## Deal Recording Sub-Agent

**Purpose**

Creates a sales opportunity inside the CRM after speaking with a prospect.

**Responsibilities**

- Finds the caller inside Pipedrive
- Creates a new Deal
- Associates the deal with the correct contact
- Updates CRM records

**External Service**

- Pipedrive CRM

---

## Demo Booking Sub-Agent

**Purpose**

Schedules product demonstrations for interested prospects.

**Responsibilities**

- Checks calendar availability
- Finds an available meeting slot
- Creates a calendar event
- Returns the booking confirmation

**External Service**

- Google Calendar

---

# Overall Workflow

The complete automation pipeline follows the process below:

```text
Ideal Customer Profile
        │
        ▼
Business Development Manager
        │
        ├── Prospecting Sub-Agent
        ├── RevOps Sub-Agent
        └── SDR Sub-Agent
                │
                ▼
         Gmail Draft Created
                │
                ▼
     Prospect Receives Email
                │
                ▼
 Prospect Calls Business Number
                │
                ▼
      Account Executive
          │
          ├── Deal Recording
          └── Demo Booking
                │
                ▼
      Pipedrive + Google Calendar
```

# Summary

| Workflow | Purpose |
|----------|---------|
| Business Development Manager | Coordinates the outbound automation pipeline |
| Prospecting Sub-Agent | Finds qualified prospects matching the ICP |
| RevOps Sub-Agent | Creates or updates CRM records |
| SDR Sub-Agent | Generates personalized outreach email drafts |
| Deal Recording Sub-Agent | Records new sales opportunities in the CRM |
| Demo Booking Sub-Agent | Schedules product demonstrations in Google Calendar |