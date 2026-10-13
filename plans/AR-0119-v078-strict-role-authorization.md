# AR-0119 plan: Coordinator v0.7.8 strict-role restoration

1. Reproduce the v0.7.8 strict-to-advisory regression on an exact clean Coordinator product
   head and correlate it with the recorded ASB AR-1852 compatibility failure and AR-0032
   upstream contract context.
2. Trace the durable role-store, lifecycle-admission, and doctor boundaries; specify the
   smallest repair that restores fail-closed authorization without changing authority, lease,
   or ownership semantics.
3. Add positive and negative contract tests for authorized, missing, unknown, stale,
   unauthorized, malformed, and replayed role/owner assignments, including doctor checks.
4. Update only Coordinator-owned runtime/tests/documentation, preserving zero-runtime-
   dependency and offline-after-install boundaries; do not touch ASB or vendored files.
5. Run focused, native, schema, privacy, formal, and required hosted gates; obtain independent
   exact-head review, publish a signed-DCO immutable result, and hand the exact release/source
   commit to ASB AR-1852 for requalification.
