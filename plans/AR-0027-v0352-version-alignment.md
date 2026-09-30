# AR-0027 plan: coordinator v0.3.52 version alignment

1. Read AR-0025, AR-0026, the release workflow, vendor tool and version tests.
2. Create a clean product worktree from the merged project-scan repair and
   identify every runtime/package/changelog version assertion.
3. Update all coupled metadata to the next unused version; add positive and
   negative mismatch tests without changing coordinator behavior.
4. Run focused/full quality, formal, privacy, DCO/signature and exact-head CI
   gates; independently review the complete diff.
5. Publish only the exact next immutable tag after fresh-clone release identity,
   contract, runbook and vendor-verification gates pass.
6. Update ASB AR-1544 with the exact released commit/manifest, leaving the
   invalid v0.3.51 tag preserved as rejected evidence.
