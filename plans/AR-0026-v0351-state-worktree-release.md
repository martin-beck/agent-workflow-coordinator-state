# AR-0026 plan: coordinator v0.3.51 state-worktree release

1. Read the coordinator release workflow and AR-0025 evidence completely.
2. Verify merge commit `2f018d9e2335b9a7e0ae04cdbc36554bde8ef60d` and the
   existing immutable `v0.3.50` identity from a clean clone.
3. Prepare the smallest valid v0.3.50-to-v0.3.51 transition and run release
   identity, contract, runbook, quality and fresh-clone checks.
4. Publish only the exact v0.3.51 tag/release after every gate is green; never
   replace an existing tag or push an unverified candidate.
5. Verify the remote tag/release and hand its exact immutable identity to ASB
   AR-1544, then release this AR with durable evidence.
