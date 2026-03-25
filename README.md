# C-Metric Public Alerts

This repository provides publicly timestamped alert logs for the preregistered C metric pipeline.

## Pipeline Status

Pipeline version: v1.0-preregistered  
Frozen as of February 28, 2026.  
No retroactive modifications permitted.  
Any future changes will increment `pipeline_version` and remain publicly traceable.

Scientific objective and working hypothesis are described in HYPOTHESIS.md.

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

## Multi layer signal logging

This repository also supports a separate transparency layer for multi layer signals.

A multi layer signal is not a prediction claim.
It is a public record of independent alignment between:

1. the public C metric alert pipeline
2. an external structural radar or instability system

Files are stored separately under:

`multilayer/YYYY/MM/`

This layer is observational and audit oriented.
It does not modify thresholds, alerts, or preregistered statistical logic.
It only records when independent systems show temporal and regional convergence.

## Monitoring Start

Prospective monitoring begins March 1, 2026.

---

This repository is intended to ensure transparency, auditability, and scientific rigor in the prospective validation of the C metric.

## Pre-Launch Testing

Test alerts may appear in the repository before March 1, 2026.

All such entries will be clearly labeled with an `alert_id` beginning with:

TEST_

These files are strictly non-operational and serve only to validate 
the alert logging structure, JSON schema integrity, and commit traceability.

No test alerts will be considered part of the prospective validation phase.

## Research Objective

This repository supports the prospective validation of the C metric
as a potential early warning indicator for systemic instability
in complex systems.

The experiment is designed to test whether sustained decreases in the
congruity metric

C = V / (E + I + S)

systematically precede extreme events in monitored systems.

All parameters, thresholds, and controls were defined prior to the
start of monitoring to ensure transparency and scientific rigor.
