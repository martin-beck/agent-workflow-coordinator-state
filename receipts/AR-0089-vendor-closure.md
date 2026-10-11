# AR-0089 vendor-closure receipt

This receipt records the exact Coordinator source that the repaired state
snapshot vendors. It is an integrity receipt, not release provenance.

## Immutable source identity

- Upstream repository: `martin-beck/agent-workflow-coordinator`
- Development channel/version: `development` / `v0.5.0`
- Upstream commit: `c8837f5a52e2d0e5c9516633ebe66885efa08235`
- Upstream tree: `85907c8ad31140558835c08a711d55bb5f493d44`
- Upstream merge: [Coordinator PR #1220](https://github.com/martin-beck/agent-workflow-coordinator/pull/1220)

The source commit and tree above are the `upstream` object in
`coordinator.vendor.json`. The manifest binds every declared destination's
source path, mode, and SHA-256 digest. Its SHA-256 at receipt creation is
`ffaa3947c32407c7050ace5521482f4417b8225c885cf453376283289ecd584a`.

## Verification evidence

- The first clean-clone verification completed in the hosted state workflow
  [Verify vendored Coordinator #38087609098](https://github.com/martin-beck/agent-workflow-coordinator-state/actions/runs/38087609098)
  at state commit `849bf9e13bb43ab7932746f90968ac408eece485`.
- A second isolated clean checkout of that same state commit passed
  `python3 tools/handoffctl_vendor.py verify --target .` on 2026-10-11.
- The repaired candidate passed the same verifier after the non-vendored
  evidence and CI changes.
- The source commit's exact-main hosted workflows passed:
  [Verify #38087259193](https://github.com/martin-beck/agent-workflow-coordinator/actions/runs/38087259193)
  and [Formal #38087259208](https://github.com/martin-beck/agent-workflow-coordinator/actions/runs/38087259208).
- The state deterministic suite passed with its pinned development dependency:
  `401` tests in `51.983s`.

## Review and publication boundary

This receipt is intentionally incomplete until an independent reviewer has
reviewed the exact state PR head and the merged head has passed both clean-clone
vendor verification and deterministic state verification. The original vendor
repair PR had no recorded independent review; this follow-up must not imply
otherwise.
