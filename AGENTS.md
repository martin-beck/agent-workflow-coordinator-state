# Coordination instructions

Read `docs/agent-workflow-coordinator.md`, the complete generated snapshot,
the selected task, and its plan before work. Claim exactly one dependency-ready
task. Route every product, Git, review, and publication mutation through
`tools/handoffctl run`.

Keep task evidence concise and public-safe. Preserve immutable vendor pins and
isolated product worktrees. Locally reproducible functional evidence is required;
external signatures, authentication, DCO, hosted approval, and independent review
are optional supplementary evidence, never progression gates. Do not edit
generated views or vendored coordinator files.
