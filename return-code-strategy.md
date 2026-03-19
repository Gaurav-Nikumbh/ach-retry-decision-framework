# Return Code Strategy

ACH return codes define how failed transactions should be handled.

## Retryable Codes

R01 — Insufficient Funds  
May be retried depending on bank policy and timing.

---

## Non-Retryable Codes

R03 — No Account  
R04 — Invalid Account  

These require user correction and should not be retried.

---

## Strategy Guidelines

- map each return code to a handling policy
- avoid retrying permanent failures
- ensure consistent handling across systems
