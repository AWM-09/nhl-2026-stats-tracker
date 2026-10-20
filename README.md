# NHL 2026–27 Stats Tracker

A fan-made NHL player and goalie statistics dashboard for the 2026–27 regular season.

## Features
- Week 1–6 filters (seven-day windows beginning 7 October 2026)
- Select individual games or include all games in the selected weeks
- Skater and goalie stat categories
- Team, position, and player search filters
- Weekly leaderboards, cumulative totals, comparisons, team view, charts, and CSV export
- Loads game schedules and completed-game boxscores from the NHL public web API

## Data and refresh behavior
The dashboard requests the latest available schedule and boxscore data from the NHL public web API when the page is opened and when **Refresh data** is pressed. GitHub Actions also republishes the site daily, matching the NFL tracker setup, but the daily deployment itself does not download or store a separate stats file: the NHL data is fetched by the dashboard in the visitor's browser.

The NHL API is public but not an official guaranteed/stable developer API. If its endpoints or response format change, the tracker may need an update. A browser/network restriction or temporary NHL API outage can also prevent loading.

## Deploy on GitHub Pages
1. Create a public GitHub repository named `nhl-2026-stats-tracker`.
2. Upload `index.html`, `README.md`, and the `.github` folder from this package to the repository's `main` branch. The `data` folder is optional and currently empty.
3. Open **Settings → Pages** and set the build/deployment source to **GitHub Actions**.
4. Open **Actions**, select **Deploy NHL tracker**, and choose **Run workflow**.
5. Once the workflow succeeds, the dashboard should be available at:
   `https://YOUR-GITHUB-USERNAME.github.io/nhl-2026-stats-tracker/`

## Daily deployment
The workflow can also be run manually from Actions. It is scheduled daily at 10:17 UTC. GitHub schedule times use UTC, so the displayed UK local time shifts when daylight saving time changes.

## Important
This is an independent fan-made tracker and is not affiliated with the NHL. Statistics are provided by the NHL public web API.
