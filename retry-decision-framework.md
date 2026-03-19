# Retry Decision Framework

ACH retry decisions should be based on structured evaluation rather than fixed rules.

## Step 1 — Identify Failure Type

Each failed transaction includes a return code.

Example:

- R01 — Insufficient Funds
- R03 — No Account
- R04 — Invalid Account

---

## Step 2 — Determine Eligibility

Not all return codes are retryable.

Retryable:
- R01 (depending on policy)

Non-retryable:
- R03
- R04

---

## Step 3 — Evaluate Timing

Retries should not occur immediately.

Typical considerations:

- time gap between attempts
- likelihood of funds availability
- bank policy constraints

---

## Step 4 — Apply Risk Controls

Before retrying, the system should evaluate:

- fraud signals
- transaction velocity
- unusual behavior patterns

---

## Step 5 — Execute Safe Retry

If eligible, the system:

- places the transaction in a retry queue
- ensures idempotency
- schedules the retry attempt

---

## Step 6 — Limit Retry Attempts

Retries should be capped.

Example:

- maximum 1 or 2 retries
- no infinite loops

---

## Step 7 — Final Outcome

If retry fails:

- mark transaction as failed
- notify the user
- log for audit and analysis
