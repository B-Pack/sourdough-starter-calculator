# 🍞 Sourdough Companion

A free, mobile-friendly sourdough starter calculator and planning tool that runs entirely in the browser.

Sourdough Companion helps home bakers calculate starter feedings, estimate when a starter may peak, work backward from a desired ready time, and record starter observations over time.

The app is built as a single standalone `index.html` file and can be hosted for free with GitHub Pages. It does not require a server, database, account, or bakery-management app.

## Features

### ⚖️ Starter Calculator

The main calculator page contains three calculation modes.

#### Initial Starter

Use this mode when you know:

- How much starter you currently have
- How much starter your recipe requires

The calculator determines:

- The required feeding ratio
- How much water to add
- How much flour to add
- The final starter yield, including reserve

#### Feed Ratio

Use this mode when you know:

- The feeding ratio you want to use
- How much starter your recipe requires

The calculator determines:

- How much existing starter to use
- How much water to add
- How much flour to add
- The total starter yield

#### Smart Custom

Enter any two of the following values:

- Current starter
- Feed ratio
- Recipe requirement

The calculator automatically solves the missing value. The calculated field fades visually and is labelled `AUTO CALCULATED`.

### Starter Reserve / Buffer

The calculator can include extra starter beyond the amount required by the recipe.

Leave the reserve field blank to use the automatic reserve:

```text
3.5% of the recipe requirement, or 30g minimum
```

Enter a value manually to keep a specific amount of starter after using the recipe portion.

Example:

```text
Recipe requirement: 500g
Starter reserve: 50g
Total starter yield: 550g
```

### ⏱️ Peak Time Estimator

The Peak Time Estimator provides an approximate range for when a fed starter may reach peak activity.

The estimate considers:

- Feeding ratio
- Temperature
- Starter condition
- Feed flour
- Relevant observations saved in the Starter Logbook

The result includes estimated stages for:

- Early rise
- Near peak
- Peak
- Past peak

Peak estimates are guidance only. Always inspect the starter itself before baking. A starter near peak commonly shows strong expansion, abundant bubbles, and a top that is still domed or only beginning to flatten.

### 📅 Feed Scheduler

The Feed Scheduler works backward from the date and time when the starter should be ready.

Enter:

- Desired ready date and time
- Feeding ratio
- Temperature
- Starter condition
- Feed flour

The scheduler returns:

- A recommended feeding time
- An estimated peak window

Because fermentation varies, the starter should still be checked before use.

### 📈 Starter Logbook

The Starter Logbook records observations such as:

- Feed date and time
- Feeding ratio
- Temperature
- Observed hours to peak
- Flour type
- Notes

Nearby observations can be used to personalize future peak-time estimates for the starter.

The app displays a calibration confidence level based on the number of saved observations:

- None
- Low
- Medium
- High

Logbook entries can also be exported as a JSON file for backup.

## Privacy and Data Storage

> **Important:** All Starter Logbook data is stored only in the browser on the current device using local storage.

The app does not upload or transmit logbook entries to a server.

Keep in mind:

- Clearing browser or site data can delete saved entries
- Private browsing may not retain entries
- Entries do not automatically transfer between browsers or devices
- Export the logbook JSON file if you want a backup

Calculator values and the selected light or dark theme are also stored locally in the browser.

## Navigation

Use the hamburger button in the top-left corner to move between:

- Starter Calculator
- Peak Time Estimator
- Feed Scheduler
- Starter Logbook

The three starter-calculation modes remain together on the Starter Calculator page.

## Light and Dark Modes

Use the theme button in the top-right corner to switch between light and dark mode.

The selected theme is remembered on the device. The first visit defaults to light mode.

## How Feeding Ratios Work

Feeding ratios are shown as:

```text
Starter : Flour : Water
```

For example, a `1:3:3` feeding uses:

```text
1 part existing starter
3 parts flour
3 parts water
```

If the existing starter amount is 20g:

```text
Starter: 20g
Flour:   60g
Water:   60g
Total:  140g
```

This calculator assumes equal flour and water feed amounts, which produces a 100% hydration feed.

## Peak-Time Disclaimer

Starter fermentation is affected by many variables, including:

- Actual starter temperature over time
- Starter maturity and condition
- Feeding history
- Flour type and freshness
- Water composition
- Hydration
- Ambient temperature changes
- Microbial culture
- Measurement accuracy

The Peak Time Estimator and Feed Scheduler intentionally return estimated ranges rather than guaranteed times. Visual and physical observations of the starter should always take priority over the timer.

## Using the App on GitHub Pages

1. Create a GitHub repository.
2. Upload the app file to the repository root.
3. Make sure the file is named exactly `index.html`.
4. In the repository settings, open **Pages**.
5. Select **Deploy from a branch**.
6. Select the `main` branch and the `/ (root)` folder.
7. Save the GitHub Pages settings.

The published address will follow this general format:

```text
https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/
```

## Repository Structure

```text
sourdough-companion/
├── index.html
└── README.md
```

No build process or third-party packages are required.

## Updating the App

To publish an update:

1. Replace or edit `index.html` in the repository.
2. Commit the change to the published branch.
3. Reload the GitHub Pages site after the deployment completes.

If an older version remains visible, refresh the page or clear the browser cache for the site.

## License

This project is available for personal and educational use. Add a formal open-source license file if you want to define redistribution and modification terms for other users.

## Happy Baking

Use the calculator as a planning aid, observe how the starter behaves, and add real peak-time observations to the logbook. The more consistent the feeding method and environment are, the more useful the personalized estimates can become.
