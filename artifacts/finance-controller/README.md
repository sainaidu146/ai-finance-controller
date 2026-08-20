# AI Finance Controller

Ledgerline is a finance-ops control center for closing a reconciliation loop with evidence.

The demo runs a synthetic 60-record batch across Stripe, Brex, NetSuite, and Mercury. It reports:

- 60 records processed
- 52 matched automatically
- 94.8% measured match quality
- 6 unresolved exceptions
- +₹184.2k net cash impact

## Run locally

From the workspace root:

```bash
pnpm install
pnpm --filter @workspace/finance-controller run dev
```

The app is intentionally local-first for this first build. The reconciliation table, evidence drawer, filters, rerun state, cash outlook, and exception resolution queue all use realistic synthetic data in Indian rupees so the control loop can be evaluated without connecting production finance systems.

## Product principle

Throughput plus measured accuracy plus an honest exception list. One cherry-picked match proves nothing.