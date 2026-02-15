# C-Metric Public Alerts

This repository provides publicly timestamped alert logs for the preregistered C metric pipeline.

## Pipeline Status

Pipeline version: v1.0-preregistered  
Frozen as of February 28, 2026.  
No retroactive modifications permitted.  
Any future changes will increment `pipeline_version` and remain publicly traceable.

## Core Definition

C = V / (E + I + S)

Where:
- V = standard deviation (system variability)
- E = Shannon entropy (KDE, Silverman bandwidth)
- I = average absolute derivative (instability)
- S = average z-score deviation (stress)

## Fixed Parameters (Preregistered)

- Baseline window: 60-day strictly pre-event reference
- Rolling window: 72 hours
- Alert threshold: >10% C drop for >6 consecutive hours
- Entropy estimation: KDE with Silverman bandwidth
- Outlier handling: Winsorization at 1% tails
- Smoothing and detrending: as defined in preregistration

## Controls Implemented

- Temporal shuffle test
- Block shuffle (6h / 12h / 24h)
- Phase randomization test
- Random time-shift placebo
- Cross-source validation where applicable

## Alert Logging

All alerts follow the JSON schema located at:

/schema/schema_v1.0.json

Alerts are stored in:

/alerts/YYYY/MM/

Each alert:
- Includes timestamp in UTC
- Is committed immediately
- Is traceable via immutable Git commit hash

## Monitoring Start

Prospective monitoring begins March 1, 2026.

---

This repository is intended to ensure transparency, auditability, and scientific rigor in the prospective validation of the C metric.
