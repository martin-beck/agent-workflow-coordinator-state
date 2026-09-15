---
{
  "branch": "fix/release-validation-dispatch",
  "checkpoint_commit": "",
  "claim_expires": "2026-09-15T21:30:03+00:00",
  "depends_on": [
    "AR-0003",
    "AR-0015"
  ],
  "id": "AR-0016",
  "next_action": "Await PR #318 Verify 35015342502 resource-profile result; retain PR #315 unmerged and use OOM evidence to guide remediation.",
  "owner": "codex-awc-ar0016-release-gate-20260915",
  "plan": "../plans/AR-0016.md",
  "priority": "P1",
  "schema_version": 1,
  "status": "in_progress",
  "summary": "PR #315 Verify 35003972069 failed at 20:02:41Z with explicit Java OOM during liveness after ~58 minutes: 46,492,959 generated, 38,466,180 distinct, 10,738,716 queued; no invariant violation. Exact head 067ba1c remains unmergeable. PR #318 is now testing the larger resource profile.",
  "task_revision": 32,
  "title": "Release validation dispatch gate",
  "updated_at": "2026-09-15T20:03:53+00:00",
  "worktree_key": "agent-workflow-coordinator-release-validation-dispatch"
}
---

Changes that affect release metadata, vendor closure, formal inputs, or
runtime packaging must execute the complete release validation tier. Path-based
pull-request optimization may remain for ordinary changes, but it must not be
the only evidence for a release candidate. The gate must preserve reproducible
CI, pinned tools, DCO/signature checks, formal evidence, and clear failure
classification without changing downstream repositories.

Acceptance: a regression test or workflow proof demonstrates that release
preparation invokes full tests, coverage, formal verification, and attestations;
ordinary non-release PRs retain their bounded fast path; documentation explains
the distinction and no release/tag is published by this AR.

- 2026-09-15T17:09:06+00:00: Promote dependency-ready AR-0016 to enforce full release validation
  dispatch after AR-0015 v0.3.8 publication.

- 2026-09-15T17:09:06+00:00: Claimed by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T17:09:29+00:00: Recorded command exit 0; command argv SHA-256
  eaf2472e4b0ec29bac3303a6d46474c99be3c0ab077feca87b1c3650d4745e53.

- 2026-09-15T17:13:01+00:00: Recorded command exit 0; command argv SHA-256
  125b299734737486b05eef62a3ccce42b47fd5db0f58f96a265e213441cb913e.

- 2026-09-15T17:13:11+00:00: Recorded command exit 0; command argv SHA-256
  81497c606ba43939fc047a6adedd96e93143b3dc32ffbbb4b6937bfa155d9efe.

- 2026-09-15T17:14:04+00:00: Recorded command exit 0; command argv SHA-256
  8766bfdc2f7cce6c84a90e92647ecc10d5e53967265cc9755ff26ef4502734cf.

- 2026-09-15T17:19:59+00:00: Recorded command exit 0; command argv SHA-256
  a3c2c97324f8a47dab44ae77163c5a2ea7a970846c1329bbcae7f7c3404ace2a.

- 2026-09-15T17:33:35+00:00: Heartbeat by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T17:33:35+00:00: Recorded command exit 0; command argv SHA-256
  134caeefc8951d357bdeac91021a4530285832c9c3c16b0448aeb2339227a69c.

- 2026-09-15T17:33:51+00:00: Recorded command exit 0; command argv SHA-256
  eaf2472e4b0ec29bac3303a6d46474c99be3c0ab077feca87b1c3650d4745e53.

- 2026-09-15T17:36:33+00:00: Heartbeat by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T17:36:33+00:00: Recorded command exit 0; command argv SHA-256
  134caeefc8951d357bdeac91021a4530285832c9c3c16b0448aeb2339227a69c.

- 2026-09-15T17:37:59+00:00: Recorded command exit 0; command argv SHA-256
  eaf2472e4b0ec29bac3303a6d46474c99be3c0ab077feca87b1c3650d4745e53.

- 2026-09-15T17:38:15+00:00: Recorded command exit 0; command argv SHA-256
  eaf2472e4b0ec29bac3303a6d46474c99be3c0ab077feca87b1c3650d4745e53.

- 2026-09-15T17:48:45+00:00: Heartbeat by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T17:50:24+00:00: Recorded command exit 0; command argv SHA-256
  76ff06647f2701d4f15186769ccf44882d01008c5e974287ead14a3ba004bfce.

- 2026-09-15T17:51:10+00:00: Recorded post-merge Verify failure 35000601242: release-sensitive push
  selected full-exhaustive but formal invocation used 1200 seconds and exited nonzero during
  Handoffctl model. Repair PR #315 published at e4ab56a602b2f915d03450faff592e6e5373ded5.

- 2026-09-15T17:52:31+00:00: Recorded command exit 0; command argv SHA-256
  e8735e72dc74959d025b4b5dca60a504b5fd726c09caba3f5b5604598131f9ae.

- 2026-09-15T17:55:49+00:00: Recorded command exit 0; command argv SHA-256
  eaf2472e4b0ec29bac3303a6d46474c99be3c0ab077feca87b1c3650d4745e53.

- 2026-09-15T17:56:54+00:00: Heartbeat by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T17:59:38+00:00: Heartbeat/status refresh: repaired PR head and public run recorded; no
  merge or release publication.

- 2026-09-15T18:06:20+00:00: Heartbeat by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T18:11:55+00:00: Heartbeat by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T18:14:58+00:00: Heartbeat by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T18:22:38+00:00: Recorded command exit 0; command argv SHA-256
  a4a355f9930e27edc3de6a6e7c7ddb65e7a9598edc474345b14a47fc89e14105.

- 2026-09-15T18:23:28+00:00: Runner diagnostics confirmed assigned formal child vanished while
  GitHub reported in_progress; restarted runner and reran failed formal job. This is classified as
  infrastructure recovery, not product pass evidence.

- 2026-09-15T19:06:35+00:00: Recorded dispatch of replacement Verify 35003972069 at 19:04:52Z;
  runner command confirms RuntimeMaxSec=6000 and active full-exhaustive TLC. No pass or merge
  claimed.

- 2026-09-15T19:06:36+00:00: Recorded command exit 0; command argv SHA-256
  c6966c2ceeea0d87b539f84dc3381b1314d4c6296469a8be5f3106a71ac421bc.

- 2026-09-15T19:30:03+00:00: Heartbeat by codex-awc-ar0016-release-gate-20260915.

- 2026-09-15T19:30:03+00:00: Recorded command exit 0; command argv SHA-256
  4750a737225f01a4e5ad2d051aa593529835756c0af1212764a2162e28af2c81.

- 2026-09-15T20:03:53+00:00: Recorded terminal PR #315 formal OOM; no model counterexample; release
  gate remains unclosed.
