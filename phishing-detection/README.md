# Phishing Detection & Response – Blue Team SOC Lab

## Overview
This project simulates a Blue Team Security Operations Center (SOC) workflow for detecting, analyzing, and responding to phishing email activity using Splunk SIEM. The goal is to demonstrate hands-on SOC analyst skills including phishing detection, investigation, indicator extraction, and incident response documentation.

## Objectives
- Detect phishing email activity using SIEM searches and dashboards
- Identify spoofed sender domains and phishing patterns
- Analyze targeted users and campaign behavior
- Extract indicators of compromise (IOCs)
- Support incident triage and response using a documented playbook

## Tools & Technologies
- Splunk Enterprise (SIEM)
- SPL (Search Processing Language)
- Simulated email security telemetry (CSV ingestion)
- Windows environment

## Data Source
Phishing data was generated using simulated email security gateway logs. Each event includes:
- Sender address and domain
- Recipient
- Subject line
- Email verdict (phish, spam, clean)
- Embedded URL or attachment metadata

This approach mirrors how SOC teams ingest and analyze email security data in production environments.

## Dashboards
The following dashboard panels were created to support phishing monitoring and investigation:
- Phishing Attempts Over Time
- Email Verdict Distribution
- Top Phishing Sender Domains
- Most Targeted Users
- Phishing URLs (Indicators of Compromise)

Screenshots of the dashboards are included to demonstrate visualization and analysis capability.

## Detection Logic
Phishing activity is detected by filtering email telemetry where the verdict is classified as phishing. Additional analysis focuses on:
- Sender domain reputation and impersonation patterns
- Subject line urgency indicators
- Number of impacted users
- Timestamp clustering to identify campaigns

## Alerts
A SIEM alert was designed to monitor for phishing activity and log detection events for analyst review. Alert logic is documented separately in the `spl-queries.md` file.

## Incident Response
A phishing incident response playbook was developed to guide analysts through:
- Alert triage and validation
- IOC extraction
- Containment actions
- Documentation and post-incident analysis

This playbook aligns with standard SOC and Blue Team practices.

## Skills Demonstrated
- Security monitoring and log analysis
- Phishing detection and investigation
- SIEM dashboard creation
- SPL query development and interpretation
- Incident response documentation
- Blue Team operational thinking

## Project Status
Completed – Portfolio Ready
