# 🍞 Sourdough Companion v5.1

A mobile-friendly sourdough starter calculator, peak-time planning tool, and offline-first starter logbook. The app is a single `index.html` file designed for free hosting on GitHub Pages.

## Version 5.1 changes

- Removed the difficult-to-measure rise multiplier from the logbook and anonymous contribution schema.
- Added separate flour choices for bleached all-purpose and unbleached all-purpose flour.
- Renamed the bread flour option to **Bread / baker's flour**. Baker's flour should be recorded using this option.
- Added a **Keep flour and water ratios symmetrical** option to Smart Custom.
- Symmetrical ratios are enabled by default and produce a 100% hydration feed.
- Unchecking the option unlocks independent flour and water ratios such as `1:2:3`.

## Main pages

### Starter Calculator

Contains three tabs:

1. **Initial Starter** calculates a feed from the starter available, recipe requirement, reserve, and desired hydration.
2. **Feed Ratio** calculates starter, flour, and water from a specified `1:F:W` ratio.
3. **Smart Custom** solves a missing value and supports both symmetrical and non-symmetrical ratios.

The automatic reserve is 3.5% of the recipe requirement or 30g, whichever is greater. A manual reserve can be entered instead.

Hydration is calculated as:

```text
Hydration % = water ratio ÷ flour ratio × 100
```

### Starter Insights

Contains three tabs:

- **Peak Estimator** provides a timing range using ratio, hydration, temperature, flour, starter condition, and nearby community observations.
- **Feed Scheduler** works backward from the desired ready time.
- **Starter Logbook** stores observations locally and can optionally contribute starter-only data to Firestore.

## Flour categories

- Bleached all-purpose
- Unbleached all-purpose
- Bread / baker's flour
- Mixed white and whole grain
- Whole wheat
- Rye-heavy

For this app, baker's flour is grouped with bread flour.

## Local storage and privacy

Full logbook entries are stored locally in IndexedDB in the current browser and device. Notes and local identifiers are not included in anonymous Firestore contributions.

Clearing browser/site data, using private browsing, or switching devices can make local records unavailable. Use **Export JSON** to create backups and **Import JSON** to restore them.

## Anonymous community contributions

When **Contribute anonymously** is checked, the app submits:

```text
flourRatio
waterRatio
hydration
temperature
flour
starterCondition
peakHours
appSource
contributeVersion
submittedByVersion
version
createdAt
```

The app does not upload the notes field or local logbook identifier.

If the device is offline, the contribution is placed in an IndexedDB upload queue and can be retried later.

## Firebase project

Version 5.1 is configured for the `sourdough-companion-167b0` Firebase project and uses the `communityObservations` Firestore collection.

The current security model allows anonymous reads and document creation, while preventing updates and deletions. Before broad public promotion, strengthen Firestore rules with field allowlists, type checks, and reasonable numeric ranges.

## GitHub Pages deployment

1. Rename the downloaded application file to `index.html`.
2. Place `index.html` and `README.md` in the repository root.
3. Open repository **Settings**, then **Pages**.
4. Choose **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`.
6. Save the Pages configuration.

Repository layout:

```text
sourdough-companion/
├── index.html
└── README.md
```

## Recommended tests

### Symmetrical Smart Custom

1. Keep **Keep flour and water ratios symmetrical** checked.
2. Enter a flour ratio.
3. Confirm the water ratio mirrors it and is visually marked as linked.
4. Confirm hydration is 100%.

### Non-symmetrical Smart Custom

1. Uncheck the symmetrical option.
2. Enter a ratio such as `1:2:3`.
3. Confirm hydration is 150%.
4. Leave one supported value blank and confirm Smart Custom solves it.

### Logbook and Firebase

1. Save a local observation with anonymous contribution disabled.
2. Confirm the row shows `Local`.
3. Save another with contribution enabled.
4. Confirm the row becomes `Synced` and a Firestore document appears.
5. Test while offline and verify the contribution shows as `Queued` until retry.

## Disclaimer

Peak timing is an estimate. Starter culture, feeding history, actual dough temperature, flour, hydration, and environmental changes all affect fermentation. Check starter expansion, bubbles, aroma, and the shape of the surface before use.
