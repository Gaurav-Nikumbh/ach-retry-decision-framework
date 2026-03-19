# Metrics and Guardrails

Retry strategies must be monitored using clear metrics.

## Key Metrics

- retry success rate
- duplicate transaction rate
- return code distribution
- retry volume

---

## Guardrails

- cap retry attempts
- enforce idempotency
- monitor processor health
- track abnormal patterns

---

## Alerting Signals

- sudden spike in retries
- increase in duplicate payments
- unusual return code patterns

These signals help prevent systemic issues.
