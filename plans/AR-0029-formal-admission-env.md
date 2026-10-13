# AR-0029 plan: formal admission environment scope repair

1. Read the upstream development, architecture, quality and formal-runner contracts and
   the downstream AR-1849 failure evidence.
2. Make the smallest workflow-only repair: define runner-private absolute
   `TLC_ADMISSION_QUEUE` and `TLC_ADMISSION_LOCK` at formal-job scope so every TLC-capable
   command, including the full unittest step, shares the same admission boundary.
3. Add positive and negative contract tests for workflow-wide propagation, absolute paths,
   and rejection of root-owned or repository-relative admission paths.
4. Run focused and full native gates, independently review the exact head, publish the PR,
   and require exact-head CI before merge or release decisions.
5. Record exact commits, checks, and downstream handoff evidence; do not modify handoffctl,
   formal models, resource limits, or gate semantics.
