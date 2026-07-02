# System Architecture

![System Architecture](system-architecture.png)

## Overview

The AI Sales Automation Platform automates both outbound sales activities and inbound customer engagement.

The solution is divided into two independent automation pipelines:

- Business Development Pipeline
- Account Executive Pipeline

---

## Business Development Pipeline

The Business Development pipeline automates outbound prospecting.

The workflow performs the following steps:

1. Receive an Ideal Customer Profile (ICP).
2. Discover companies and decision makers matching the ICP.
3. Create or update contacts inside Pipedrive CRM.
4. Generate personalized outreach email drafts.
5. Save the draft in Gmail for review before sending.

---

## Account Executive Pipeline

After receiving an outreach email, a prospect can call the dedicated business phone number.

The Account Executive pipeline automatically handles the conversation by:

1. Recording the caller as a sales opportunity.
2. Creating a Deal inside Pipedrive.
3. Booking a suitable demo time.
4. Creating a Google Calendar event.

---

## Technologies

- n8n
- Pipedrive CRM
- Gmail
- Google Calendar
- Twilio
- ElevenLabs