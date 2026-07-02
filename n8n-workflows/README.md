# n8n Workflows

This directory contains the n8n workflows that power the AI Sales Automation Platform.

The workflows are organized into two functional groups:

- **Business Development** – automates outbound sales activities, including prospect discovery, CRM enrichment, and personalized outreach.
- **Account Executive** – automates inbound customer interactions, including recording new sales opportunities and scheduling product demonstrations.

---

## Folder Structure

```text
n8n-workflows/
├── account-executive/
│   ├── deal-recording-sub-agent.json
│   └── demo-booking-sub-agent.json
│
└── business-development/
    ├── business-development-manager.json
    ├── prospecting-sub-agent.json
    ├── revops-sub-agent.json
    └── sdr-sub-agent.json
```

---

# Business Development

This group is responsible for the outbound sales pipeline.

| Workflow | Description |
|----------|-------------|
| `business-development-manager` | Orchestrates the outbound sales workflow by coordinating the supporting workflows. |
| `prospecting-sub-agent` | Identifies companies and decision makers that match the provided Ideal Customer Profile (ICP). |
| `revops-sub-agent` | Creates and updates CRM records for qualified prospects. |
| `sdr-sub-agent` | Generates personalized outreach emails and creates Gmail drafts for review. |

---

# Account Executive

This group supports inbound sales interactions.

| Workflow | Description |
|----------|-------------|
| `deal-recording-sub-agent` | Records a new sales opportunity in the CRM when a qualified prospect contacts the business. |
| `demo-booking-sub-agent` | Schedules a product demonstration and creates a corresponding Google Calendar event. |

---

## Notes

- All workflows are designed to operate independently and communicate through APIs and webhooks.
- Each workflow has a single responsibility, making the system modular, reusable, and easy to maintain.
- Sensitive information such as API keys, credentials, and webhook URLs has been removed from the exported workflow files.