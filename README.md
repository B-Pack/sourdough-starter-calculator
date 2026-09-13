# 🍞 Sourdough Companion v6.0

Sourdough Companion v6 is a single-file, offline-first fermentation intelligence platform for GitHub Pages. It combines personal starter records, Firestore community statistics, and predictive models.

## V6 features
- Multiple local starter profiles
- Starter Timeline for feed, peak, bake/use, collapse, and note events
- Feed Planning Assistant with ready, dough-mix, and bulk-fermentation targets
- Starter Health Score, peak trend, consistency, and refrigeration recovery
- Dynamic 0–100 confidence score
- Most-likely peak plus 80% and 95% confidence windows
- Community Insights using `communityStatistics`
- Ratio presets on ratio-based tools only
- IndexedDB migration that preserves existing stores and adds profile, timeline, and scheduler stores
- Reusable `buildObservationPayload()`
- Anonymous validation before upload

## Storage
IndexedDB database: `SourdoughCompanion`, version 8. Existing `starterLogs`, `pendingUploads`, and `communityCache` data are preserved. New stores are `starterProfiles`, `timelineEvents`, and `schedulerTargets`. Existing logs without a `starterId` remain compatible and can be treated as Main Starter data during migration.

## Firebase
Project: `sourdough-companion-167b0`

Raw anonymous submissions are created in `communityObservations`. Community dashboards read `communityStatistics`. The public app does not update aggregate documents.

## communityStatistics document
```json
{
  "flourRatio": 5,
  "waterRatio": 5,
  "hydration": 100,
  "temperatureBucket": 22,
  "flour": "bread",
  "starterCondition": "strong",
  "samples": 251,
  "averagePeak": 8.2,
  "standardDeviation": 0.8,
  "version": 1
}
```

## Deployment
Place `index.html` and `README.md` in the repository root and deploy the root of the main branch with GitHub Pages.

## Privacy
Profiles, notes, timelines, and scheduler targets remain on-device. Only the established anonymous observation schema is uploaded. No accounts or authentication are used.

## Disclaimer
Predictions and health scores are planning aids. Confirm readiness from starter expansion, bubbles, aroma, and surface shape.
