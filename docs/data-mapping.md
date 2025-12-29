# Synthetic Cloud Security Telemetry Mapping

This project uses a synthetic dataset to simulate cloud security and operational telemetry.

| Dataset Field | Security Interpretation |
|--------------|-------------------------|
| City | Azure Region / Resource Group |
| Temperature | Risk Score |
| Humidity | Configuration Drift Level |
| WindSpeed | Threat Velocity |
| WeatherDesc | Security Event Type |
| EventTime | Event Timestamp |

This approach allows controlled testing of security detection logic
without relying on live production data.
