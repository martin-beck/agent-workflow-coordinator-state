# AR-0089 vendor-closure receipt

This receipt records the exact Coordinator source that the repaired state
snapshot vendors. It is an integrity receipt, not release provenance.

## Immutable source identity

- Upstream repository: `martin-beck/agent-workflow-coordinator`
- Release channel/version: `release` / `v0.5.0`
- Upstream commit: `3f644ac6353dc70e1729d1b1369c18e7d2c5adb8`
- Upstream tree: `3481191a1349bdaa652245b7c9768becbe3872ba`
- Upstream release: [Coordinator v0.5.0](https://github.com/martin-beck/agent-workflow-coordinator/releases/tag/v0.5.0)

The source commit and tree above are the `upstream` object in
`coordinator.vendor.json`. The release manifest binds every declared
destination's source path, mode, and SHA-256 digest; the release tag resolves
the source tree above. Its SHA-256 at receipt creation is
`8ffed9842df9faf343d1cf74b7d8b1d27d4efc010ae79abd93d8a18b1f5097c6`.

## Verification evidence

- State PR [#16](https://github.com/martin-beck/agent-workflow-coordinator-state/pull/16)
  was independently reviewed at exact candidate
  `0f54f97b73b32dd9589c567d402e659929db64e3`. The review confirmed that the
  release-snapshot rebuild distinguishes schema-1 tagged releases from
  schema-2 development snapshots, and found no defect in the candidate.
- The reviewed candidate passed both required checks:
  [deterministic state verification](https://github.com/martin-beck/agent-workflow-coordinator-state/actions/runs/38121869453)
  and [clean-clone vendor verification](https://github.com/martin-beck/agent-workflow-coordinator-state/actions/runs/38121869465).
- The merged exact-main state commit
  `8bd6034dc692dd101648703514b4161e682777c7` passed the same two independent
  gates again:
  [deterministic state verification](https://github.com/martin-beck/agent-workflow-coordinator-state/actions/runs/38121984920)
  and [clean-clone vendor verification](https://github.com/martin-beck/agent-workflow-coordinator-state/actions/runs/38121984916).

The two clean-clone passes above cover both the independently reviewed
candidate and the exact merged main tree. Earlier c8837f evidence is historical
and is not used as v0.5.0 qualification.

## Review and publication boundary

The reviewed source, candidate, and exact merged main checks above establish
the downstream vendor-integrity boundary. This receipt does not assert release
provenance beyond the cited upstream v0.5.0 release identity.
