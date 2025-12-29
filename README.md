# Event-Driven Cloud Security Alert Platform (Azure)

## Overview
This project demonstrates a serverless, event-driven cloud security analytics platform built on Microsoft Azure.
The platform processes streaming telemetry events, detects risks, misconfigurations, and anomalies in real time,
and generates security alerts using Azure Functions and Azure Event Grid.

A synthetic telemetry dataset is used to simulate cloud operational and security events across multiple regions.

---

## Architecture
The system follows an event-driven architecture:

1. Telemetry events are stored in Azure SQL Database
2. An Azure Function analyzes new events using detection rules
3. High-risk events are published to Azure Event Grid
4. A second Azure Function processes and classifies alerts
5. Alerts are stored for monitoring and visualization

---

## Detection Logic
The platform identifies security-relevant conditions such as:
- High-risk activity based on abnormal risk scores
- Configuration drift indicators
- Anomalous event velocity
- Critical event types

Each event is evaluated and assigned a severity level.

---

## Technologies Used
- Azure Functions
- Azure Event Grid
- Azure SQL Database
- Azure Monitor / Log Analytics
- Event-Driven Architecture
- Serverless Security Analytics

---

## Use Cases
- Cloud security monitoring
- Misconfiguration detection
- Anomaly detection
- Real-time alerting pipelines

---

## Future Enhancements
- Machine learning-based anomaly detection
- Integration with Azure Sentinel
- Real cloud activity logs
- Advanced alert visualization dashboards
