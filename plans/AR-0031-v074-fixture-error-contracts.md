# AR-0031 plan: Coordinator v0.7.4 fixture and error contracts

1. Reproduce the vendor-manifest and AR-1793 fixture failures against the exact v0.7.4 adoption.
2. Identify the intended public error and fixture contracts; preserve negative behavior and privacy.
3. Update only compatibility fixtures/tests and narrowly required contract assertions, with positive and hostile cases.
4. Run focused and full native/AWQ/schema/privacy gates plus independent exact-head review.
5. Hand the exact reviewed result to AR-0032 and AR-0033; do not modify AR-1849-owned runtime seams.
