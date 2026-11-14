# it-ops-dashboard-jamf-zapier

A live IT operations dashboard pulling device fleet data from Jamf Pro, built on a self-hosted Zapier MCP connection rather than a shared/inherited integration.

## Problem

IT fleet health (enrollment status, compliance, stale devices) is easy to lose track of when it only lives inside the Jamf console. A single-glance dashboard surfaces the state of the managed fleet without logging into Jamf directly every time.

## Approach

Built a dashboard that pulls managed-computer data from Jamf Pro as a live data source, delivered on a recurring schedule to a single notification channel rather than paging through multiple daily digests. Set up an independent Zapier MCP server connection to Jamf, rather than relying on a shared team connection, so the integration's credentials and failure modes are owned directly.

## What It Does

- Surfaces managed macOS fleet status (enrollment, compliance, last check-in) from Jamf Pro
- Delivers a daily summary link to a single channel rather than a full inline digest, to avoid duplicating an existing daily recap
- Runs on an independently owned Zapier MCP connection, isolated from shared team credentials

## Tech Stack

- Jamf Pro API (managed computers endpoint)
- Zapier (MCP server integration)
- Dashboard/notification delivery layer

## Notes

Device identifiers, organization name, and connection credentials have been generalized or removed. This documents the architecture and data flow, not a working export of the dashboard configuration.

---

**Security note:** Never commit real credentials, API keys, tenant IDs, internal URLs, or any company-identifying data. Replace with placeholders before publishing, and check commit history too.
