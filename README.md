# 🍞 Sourdough Companion

Sourdough Companion Version 7 is a focused, mobile-friendly starter calculator and optional peak-observation tool. It is designed as a single `index.html` file for GitHub Pages.

## Version 7 scope

Version 7 intentionally returns the application to its original purpose:

1. Calculate starter feed quantities.
2. Optionally estimate peak timing using personal and community observations.

Features that belonged more naturally in the Bakery App, including multiple starter profiles, starter timelines, dough-mixing targets, bulk-fermentation targets, and biological health scoring, have been removed.

## Included features

### Starter Calculator

- Initial Starter
- Feed Ratio
- Smart Custom
- Automatic starter reserve
- Symmetrical ratios by default
- Independent flour and water ratios for advanced feeds
- One-tap presets where ratios are actual inputs

Initial Starter intentionally does not display ratio presets because its feed ratio is calculated from the available starter, recipe requirement, reserve, and hydration.

### Peak Planner

Peak Estimator and Feed Planning Assistant are combined into one page with two modes:

- **Estimate My Peak** shows the most likely peak plus 80% and 95% confidence windows.
- **When Should I Feed?** works backward from a desired ready time.

The planner uses the feed ratio, temperature, flour, starter condition, matching local observations, valid community statistics, and the generic fallback model.

### Starter Logbook

- Add observations
- Edit local observations
- Delete local observations
- Retry pending uploads
- Export JSON
- Import JSON
- Anonymous Firestore contribution
- Offline queue

The Your Starter Data card reports factual measurements rather than a health score:

- Observation count
- Average peak
- Typical variation
- Fastest and slowest recorded peaks
- Most-used ratio
- Prediction-readiness label

### Community Insights

The dashboard reads valid aggregate documents from `communityStatistics` and displays:

- Total samples
- Statistic bucket count
- Common feeding ratios
- Common hydration levels
- Average peak by flour
- Average peak by temperature

Placeholder documents without sample counts and peak averages are ignored.

## Technology

- Single `index.html`
- Vanilla HTML, CSS, and JavaScript
- GitHub Pages
- IndexedDB
- Firebase Firestore
- No framework
- No build process
- No authentication
- Offline-first local logbook and upload queue

## Firebase project

Project: `sourdough-companion-167b0`

Collections:

- `communityObservations`: append-only anonymous observations
- `communityStatistics`: read-only aggregate documents for public clients

## Observation schema

```json
{
  "flourRatio": 5,
  "waterRatio": 5,
  "hydration": 100,
  "temperature": 22.5,
  "flour": "bread",
  "starterCondition": "strong",
  "peakHours": 8.4,
  "appSource": "Sourdough Companion",
  "contributeVersion": "1",
  "submittedByVersion": "7.0.0",
  "createdAt": "server timestamp",
  "version": 1
}
```

The reusable `buildObservationPayload()` function preserves compatibility with the future Bakery App integration layer.

## Community statistics schema

```json
{
  "flourRatio": 5,
  "waterRatio": 5,
  "hydration": 100,
  "temperatureBucket": 22,
  "flour": "bread",
  "starterCondition": "strong",
  "samples": 1,
  "averagePeak": 8.4,
  "standardDeviation": 0,
  "version": 1
}
```

## Data validation

Anonymous contributions are rejected when:

- Peak time is below 1 hour or above 72 hours
- Hydration is below 20% or above 300%
- Temperature is below 0°C or above 50°C
- Flour or water ratios are not positive

## IndexedDB compatibility

Version 7 continues using the existing `SourdoughCompanion` database and preserves:

- `starterLogs`
- `pendingUploads`
- `communityCache`

Legacy stores created by Version 6 are not deleted, but Version 7 does not use them. Existing Version 5.3 logbook records remain readable.

## Deployment

1. Rename the downloaded HTML file to `index.html`.
2. Place `index.html` and `README.md` in the repository root.
3. Deploy the repository root through GitHub Pages.
4. Keep the same Pages URL to preserve access to existing IndexedDB data.

## Recommended testing

- Confirm the page header says only **Sourdough Companion**.
- Confirm navigation highlights only the currently selected page.
- Confirm Initial Starter has no ratio presets.
- Test symmetrical and non-symmetrical feeds.
- Test both Peak Planner modes.
- Confirm no Invalid Date appears in confidence windows.
- Add, edit, and delete a logbook observation.
- Test anonymous upload, offline queue, and retry.
- Export and re-import the logbook.
- Confirm valid `communityStatistics` documents appear in Community Insights.

## Disclaimer

Peak predictions are planning estimates. Check starter expansion, bubbles, aroma, and surface shape before use.
