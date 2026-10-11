# Development policy

The product is `martin-beck/agent-workflow-coordinator`; this repository is
its Git-backed coordination state. Read the vendored coordinator guide and
complete snapshot before every task.

Workers claim one `open` task, use its named product branch/worktree, and run
all product, Git, review, and publication commands through `tools/handoffctl
run`. Record concise results immediately, release the task truthfully, then
reconcile and run `tools/handoffctl doctor --live` when live configuration is
available.

The state repository must retain the exact coordinator vendor manifest and
never contain credentials, prompts, raw logs, private paths, hostnames, or
machine-specific configuration. AWQ policy files belong to the product
repository and must pin an immutable released AWQ commit while retaining all
native product gates.

## Local verification

Install the pinned development test dependencies, then run the deterministic
state suite from the repository root:

```sh
python -m pip install -r requirements-dev.txt
PYTHONDONTWRITEBYTECODE=1 python -m unittest discover -s tests -p 'test_*.py'
```

The `Verify Coordinator state` workflow runs this same suite for pull requests
and pushes to `main`. It complements, rather than replaces, the separate
clean-clone vendor verification workflow.
