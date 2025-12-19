---
title: "Wazuh Lab: Overview + Minimal Setup"
---

# Wazuh Lab: Overview + Minimal Setup

This article sets up a minimal Wazuh lab and explains the core components so you can start building detections and testing rules.

## Audience
SOC analysts, security engineers, and anyone learning SIEM + endpoint telemetry.

## What you will build
- 1x Wazuh Manager
- 1x Wazuh Agent (Linux or Windows)
- Basic event flow verification (agent → manager → alerts)

## Wazuh in 90 seconds (components)
- **Agent:** runs on endpoints, collects logs, monitors integrity, and ships events.
- **Manager:** receives events, applies decoders/rules, generates alerts.
- **Indexer / Dashboard (if enabled):** stores alerts and provides search/visualization.

## Lab prerequisites
- A VM or server (Linux) for the manager
- An endpoint for the agent (Linux or Windows)
- Network connectivity between them
- Admin/root access

## Step 1 — Install the manager
> Add your chosen installation method here (single-node / docker / package install).
- Verify the service is running
- Confirm ports are listening

**Validation**
- Manager status shows healthy
- Dashboard (if used) is reachable

## Step 2 — Install the agent
- Install the agent on the endpoint
- Register it to the manager
- Start the agent service

**Validation**
- Agent shows as connected/active on the manager

## Step 3 — Generate a test event
- Create a simple log event (Linux auth log / Windows security event)
- Confirm it appears in Wazuh alerts

**Validation**
- You can search and find the event in the dashboard (or manager logs)

## Common issues
- Agent not connecting (firewall / wrong manager IP / registration key)
- Time sync issues (NTP drift)
- Dashboard not showing data (indexer/downstream issue)

## Next steps
- Add Sysmon (Windows) or auditd (Linux)
- Start writing custom rules and testing them with sample logs

## References
- Wazuh documentation (add links you used)
