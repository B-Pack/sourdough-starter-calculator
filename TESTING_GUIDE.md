# Sourdough Companion V6 Testing Guide

## Regression
- Test Initial Starter, Feed Ratio, and Smart Custom.
- Confirm Initial Starter has no ratio presets.
- Confirm symmetrical and advanced ratios work elsewhere.
- Verify hydration calculation and reserve behavior.

## Profiles
- Create Main, Rye, and Experimental starters.
- Switch profiles and confirm logs, health, timeline, and plans are filtered.
- Reload and confirm the active profile persists.

## Timeline
- Add feed, peak, bake/use, and collapse events.
- Confirm newest-first calendar display and profile isolation.

## Planning and predictions
- Enter ready, mixed, and bulk targets.
- Verify suggested feed time and peak window.
- Add matching observations and confirm confidence changes.
- Confirm 80% is narrower than 95%.

## Health
- Verify empty-state behavior.
- Add multiple observations and verify average, trend, consistency, and score.
- Add weak/refrigerated observations and verify recovery reporting.

## Firebase
- Save an anonymous observation and verify `communityObservations`.
- Test invalid peak, hydration, and temperature limits.
- Add a valid `communityStatistics` document and refresh Community Insights.
- Test offline queue and retry.

## Backup
- Export V6 JSON.
- Import into a clean browser profile.
- Confirm profiles, logs, timelines, and scheduler targets restore.
