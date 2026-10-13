# AR-0030 plan: release metadata and tag alignment

1. Inspect the release identity, metadata, vendor checks, and accepted task/release contracts.
2. Make the smallest product change aligning runtime metadata and tests to the next immutable
   release version; preserve v0.7.3 unchanged.
3. Run focused and full native gates, privacy checks, independent exact-head review, and required
   hosted CI.
4. Merge only the exact reviewed head, verify protected-main post-merge checks, then publish a
   signed immutable successor tag/release whose runtime metadata matches.
5. Record exact commit/tag/release evidence and hand the corrected release to downstream ASB.
