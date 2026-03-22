# soc-soar-threat-intel-platform


# Phase 1 — SIEM Foundation

## Goal
Set up centralized logging using ELK stack (Elasticsearch, Logstash, Kibana) and Beats (Filebeat for Linux, Winlogbeat for Windows).  
This forms the foundation for log ingestion, search, and later detection.

## Stack Used
- Elasticsearch
- Logstash (optional)
- Kibana
- Filebeat (Linux logs)
- Winlogbeat (Windows logs)

## Setup Guide

### 1. Install ELK Stack
- Follow official documentation for Elasticsearch, Logstash, Kibana
- Ensure all services are running

### 2. Configure Beats
- Filebeat (Linux) → `configs/filebeat.yml`  
- Winlogbeat (Windows) → `configs/winlogbeat.yml`  

Example configuration snippets:

```yaml
filebeat.inputs:
- type: log
  paths:
    - /var/log/*.log

winlogbeat.event_logs:
- name: Security
- name: System
