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

## Canary releases

Ship to a small slice of traffic, compare SLIs with baseline, then promote or roll back automatically.

## Runbooks

Every page should link to a runbook: what it means, how to verify, how to mitigate, who to escalate to.

## Capacity planning

Track saturation trends and forecast; provision for peak plus N+1 redundancy, not average load.

## Graceful degradation

Prefer serving stale or partial results over failing completely when a dependency is down.

## On-call hygiene

Fewer than two pages per shift; every page must be actionable, otherwise fix or delete the alert.

## Load shedding

Reject excess requests early (429/503) to protect the service instead of degrading for everyone.

## Retries with jitter

Use exponential backoff with jitter and a retry budget to avoid thundering herds.

## Change management

Most outages come from changes: progressive rollouts, feature flags and fast rollback reduce blast radius.
