#🛡️ Cybertr0n SOC Infrastructure Build – Phase 1

Author: Orinea Mulaudzi
Status: Operational
Focus Area: SOC Visibility & Endpoint Telemetry
Tools: Wazuh SIEM/XDR, Ubuntu Linux, Windows 10/11, PowerShell

#📌 Project Overview

This project represents Phase 1 of the Cybertr0n SOC Infrastructure Build, focused on eliminating security blind spots by establishing centralized visibility over a Windows endpoint using an open-source SIEM/XDR platform.

The objective of this phase was not alerting or incident response, but foundational SOC visibility — ensuring reliable telemetry, secure agent communication, and verifiable data flow between endpoints and the SIEM manager.

#🎯 Objectives

Deploy a centralized Wazuh SIEM/XDR Manager

Securely onboard a Windows endpoint as a monitored agent

Validate encrypted communication and data ingestion

Enable core SOC visibility capabilities with zero licensing cost

Produce operational proof suitable for SOC documentation

#🏗️ Architecture

The lab follows a Manager–Agent architecture, commonly used in enterprise SOC environments:

Component	Role	OS	Status
Wazuh Manager	SIEM/XDR, Indexer & Dashboard	Ubuntu Linux	Running
Windows Endpoint	Monitored Agent	Windows 10/11	Active

This design enables centralized analysis with decentralized data collection, mirroring real-world SOC deployments.

#🛠️ Implementation Summary

Phase 1 was executed across three core stages:

Manager Provisioning

Deployed a single-node Wazuh stack on Ubuntu

Enabled analysis engine, indexer, and dashboard

Agent Deployment

Installed Wazuh agent on Windows via PowerShell

Configured system services for persistence

Secure Enrollment

Manually authenticated agent using unique auth keys

Established encrypted TLS communication over port 1514

#🔍 Security Capabilities Enabled

The following SOC-relevant capabilities were successfully activated:

Log Management
Collection of Windows Event Logs (e.g. 4624, 4625) for authentication auditing

File Integrity Monitoring (FIM)
Detection of unauthorized system file changes

Security Configuration Assessment (SCA)
Baseline auditing against CIS benchmarks

Vulnerability Detection
Continuous CVE scanning to identify outdated or vulnerable software

#🧪 Verification & Proof of Functionality

Operational verification was performed to ensure reliability beyond the web interface:

Agent status confirmed via agent_control -l

Heartbeat telemetry validated in the Wazuh dashboard

System inventory (CPU, RAM, applications) successfully ingested

Backend health confirmed through CLI and log analysis (ossec.log)

Screenshots included in the PDF provide availability, integrity, and data-flow proof.

#🧠 Key Learning Outcomes

This phase emphasized real-world troubleshooting rather than guided installation:

Virtualization recovery after VM save-state corruption

Windows pathing, permissions, and PowerShell execution policies

Manual service recovery and validation

Differentiating frontend (dashboard) issues from backend health

These challenges developed functional SOC knowledge — understanding how SIEM components communicate, fail, and recover.
