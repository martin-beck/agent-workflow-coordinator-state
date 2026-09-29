# AR-0024 plan: self-consistent vendor snapshot publication

1. Read the coordinator vendor contract, `tools/vendor.py`, the v0.3.50
   release history and the downstream ASB AR-1534 failure evidence. Reproduce
   the exact mismatch in a disposable state target.
2. Make the vendor source manifest and installer self-consistent: every module,
   schema, formal artifact and test imported by the published `handoffctl`
   must be included in one allowlisted atomic snapshot, including the vendor
   helper itself. A failed staging or verification step must leave the target
   unchanged.
3. Add positive and negative tests for clean sync, missing source files,
   post-install verification and rerunning the verifier from the installed
   target. Preserve symlink, path, privacy and immutable-source checks.
4. Run the complete coordinator suite, strict types/lints/format, formal and
   vendor tests. Independently review the full diff and signed+DCO history,
   then publish a reviewed PR and wait for exact-head hosted checks.
5. Publish the next immutable coordinator release only after the merged head
   passes all required gates. Downstream ASB must consume that fresh release;
   no downstream manifest edits or gate bypasses are permitted.

Acceptance: a fresh downstream state can atomically vendor the released
coordinator, run the installed vendor verifier and then run `handoffctl` with
no missing modules or digest drift; failed syncs leave no partial snapshot.
