# Wazuh-Shellshock-Detection
Wazuh SIEM lab demonstrating Shellshock attack detection through Apache access logs.
# Wazuh Shellshock Attack Detection

## Project Overview
This project demonstrates the detection of a Shellshock-pattern HTTP request using Wazuh SIEM and Apache access logs in a controlled cybersecurity lab.

## Lab Environment
- **Attacker:** Kali Linux — `192.168.1.104`
- **Victim:** Ubuntu Linux / Apache — `192.168.1.103`
- **Wazuh Manager:** `192.168.1.102`

## Objective
Validate that Wazuh can identify a suspicious HTTP request containing a Shellshock-style payload and generate a security alert.

## Methodology
1. Verified that Apache was running on the Ubuntu endpoint.
2. Restarted the Wazuh agent and confirmed it was active.
3. Sent a crafted HTTP request from Kali Linux to the Ubuntu web server.
4. Reviewed the Apache access log.
5. Investigated the resulting Wazuh alert.

## Detection Results
- **Alert:** Shellshock attack detected
- **Wazuh Rule ID:** `31168`
- **Severity:** Level 15
- **Rule groups:** `web`, `accesslog`, `attack`
- **Source IP:** `192.168.1.104`
- **Destination IP:** `192.168.1.103`
- **HTTP response:** `200`

## Key Learning
The exercise demonstrates how Wazuh can detect suspicious web requests through log monitoring and support incident investigation.

**Important:** The alert confirms detection of the suspicious request, but the available evidence does not establish that the injected command executed or that the server was successfully exploited.

## Project Evidence
See the accompanying Word report for the lab methodology, screenshots, alert details, analysis, and conclusion.

## Reference
[Wazuh — Detecting a Shellshock web attack](https://documentation.wazuh.com/current/proof-of-concept-guide/detect-web-attack-shellshock.html)
