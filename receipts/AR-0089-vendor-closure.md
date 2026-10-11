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

- The v0.5.0 candidate's two clean-clone verifications, deterministic state
  suite, independent review and exact-main checks are recorded only after its
  own PR reaches a reviewed head. Earlier c8837f evidence is historical and
  must not be used as v0.5.0 qualification.

## Review and publication boundary

This receipt is intentionally incomplete until an independent reviewer has
reviewed the exact v0.5.0 state PR head and the merged head has passed both
clean-clone vendor verification and deterministic state verification. The
earlier c8837f repair and its follow-up do not substitute for this review.
