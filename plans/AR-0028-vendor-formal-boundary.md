# AR-0028 plan: coordinator vendor formal-boundary repair

1. Read the coordinator development/architecture/quality documentation and
   the complete AR-0027 plus ASB AR-1547/1548 evidence.
2. Inventory the coordinator vendor source list, generated lock and tests;
   classify every formal artifact as coordinator-owned or ASB-owned.
3. Remove ASB-owned formal models, tier evidence, attestation helper and
   launcher/configuration files from the coordinator allowlist. Keep runtime
   libraries, schemas and coordinator-owned formal evidence intact.
4. Add positive/negative tests for the exact allowlist and update docs.
5. Run focused vendor tests, the full coordinator suite, lint/type/privacy
   gates and an independent diff/signature/DCO review.
6. Publish the next immutable release, verify a fresh clone and hand ASB the
   exact tag, commit and manifest digest. Do not consume or retag v0.3.51 or
   v0.3.52.
