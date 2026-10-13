# AR-0033 plan: Coordinator v0.7.4 complexity contract

1. Reproduce the exact workflow complexity failure and identify the reviewed v0.7.4 source set.
2. Update the command/expectation contract to cover that set without lowering CCN, excluding files, or weakening CI.
3. Add positive and negative regression coverage for missing, extra, and under-threshold command arguments.
4. Run workflow, privacy, full native/AWQ, and exact-head review gates.
5. Hand off the exact reviewed workflow repair for integrated v0.7.4 requalification.
