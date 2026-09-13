# Sourdough Companion V6 Migration Notes

## Compatibility
- Firebase project configuration and raw observation schema are unchanged.
- Existing Firestore observations remain valid.
- IndexedDB is upgraded in place from earlier versions to version 8.
- Existing object stores are never deleted.
- New stores: `starterProfiles`, `timelineEvents`, and `schedulerTargets`.
- A Main Starter profile is created automatically if no profile exists.

## Before deployment
1. Export a JSON backup from V5.3.
2. Replace the repository `index.html`.
3. Keep the same GitHub Pages URL so the browser can access the existing IndexedDB origin.
4. Reload once and verify Main Starter appears.
5. Confirm old logs remain visible.

## communityStatistics
The placeholder document with only `placeholder: true` is ignored. Add real aggregate documents using the schema in README.md. Public clients should have read access but not create, update, or delete access to `communityStatistics`.

Because V6 has no backend server, V6 does not safely maintain shared aggregate documents from anonymous browsers. Populate aggregates manually during early testing or use a trusted administrative process outside the public application.
