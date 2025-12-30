# Security Detection Logic

This document defines the rule-based detection logic used to analyze synthetic cloud telemetry events
and generate security alerts within the event-driven platform.

---

## Alert Conditions

The following conditions are evaluated for each telemetry event:

### 1. High-Risk Activity
Triggered when the event risk score falls outside expected operational bounds.

- Condition:
  - `riskScore < -2` OR `riskScore > 28`

---

### 2. Configuration Drift
Indicates potential misconfiguration or policy deviation.

- Condition:
  - `driftLevel > 90`

---

### 3. Anomalous Activity
Represents unusually high event frequency or threat velocity.

- Condition:
  - `threatVelocity > 40`

---

### 4. Critical Event Types
Certain event types are always treated as high-impact.

- Condition:
  - `eventType IN ["Thunderstorm", "Heavy Rain"]`

---

## Severity Classification

Severity is determined based on the number of triggered detection rules per event:

| Triggered Rules | Severity  |
|-----------------|-----------|
| 1               | Medium    |
| 2               | High      |
| ≥ 3             | Critical  |

---

## Alert Generation

Events meeting one or more alert conditions are forwarded to the alert processing pipeline via
Azure Event Grid for further classification and storage.
