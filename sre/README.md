# SRE notes

Short, practical notes collected while studying and testing.

## Error budget

Error budget = 1 - SLO. For 99.9% over 30d: ~43m12s of allowed downtime.

## Four golden signals

Latency, traffic, errors, saturation.

## Toil

Manual, repetitive, automatable work that scales linearly with service growth. Keep it under 50%.

## Blameless postmortem

Focus on what happened and why the system allowed it, not who. Always end with owned action items.

## SLI vs SLO vs SLA

SLI = measurement, SLO = internal target, SLA = contract with consequences.

## Alert on symptoms, not causes

Page on user-facing impact (error rate, latency); keep cause-based alerts as tickets or dashboards.
