# Profile maintenance

## Sources

Only existing public project material is used. The interface previews are copied unchanged; the Alteryx and SQL previews are illustrations from their repositories, not new screenshots of a running installation.

| File | Public source revision |
| --- | --- |
| `assets/ruycast.png` | [Ruycast `assets/hero.png`](https://github.com/viggomeesters/ruycast/blob/ceb43e7d578c66689d52c75a6dde523995e1f512/assets/hero.png) |
| `assets/alteryx-viewer.svg` | [Alteryx Viewer `assets/screenshot.svg`](https://github.com/viggomeesters/obsidian-alteryx-viewer/blob/19d4050ca2392bc8f8a5609df8545e40737c1d85/assets/screenshot.svg) |
| `assets/sql-viewer.svg` | [SQL Viewer `assets/screenshot.svg`](https://github.com/viggomeesters/obsidian-sql-viewer/blob/cac87886da897e17d765f035acd6ba0384e5269c/assets/screenshot.svg) |

Descriptions follow the public project READMEs. Ruycast is a native beta, not a notarized app release. Project links remain the source for installation and current status.

## Metrics snapshot

Generated on **16 November 2026** by [lowlighter/Metrics v3.34](https://github.com/lowlighter/metrics/tree/65836723097537a54cd8eb90f61839426b4266b6), commit `65836723097537a54cd8eb90f61839426b4266b6`. This is a committed snapshot, not a live service. It uses the classic template, public owned repositories (including forks), their reported language bytes, and the full-year isometric contribution calendar.

Language proportions describe repository contents, not proficiency or time spent. GitHub contributions are attributed activity, not every commit present in repository history. The calendar may include anonymized private contributions already exposed by the public profile; it contains no private repository names or content. Metrics aligns its yearly calendar to whole weeks, so its period begins 16 November 2025 and ends on the generation date.

The shared service returned HTTP 500 during preparation. The snapshot was rendered once locally using upstream Metrics, existing Node.js and an existing headless Chrome installation. There is no hosted process, GitHub Action or scheduled refresh.

### Manual refresh

1. Check out the pinned upstream Metrics revision in an isolated temporary directory, outside this profile repository.
2. Apply [`metrics-public-only.patch`](metrics-public-only.patch). This bounded adaptation of existing upstream JavaScript/GraphQL restricts repository queries to `privacy: PUBLIC` and owned repositories; disables broad fallback, account contribution-history search, contributed-repository listing and package queries; and retains only calendar colors in the base query. The unmodified isocalendar plugin requests dates, colors and anonymized daily contribution counts. No renderer, chart or statistic is reimplemented.
3. Install the pinned upstream dependencies with lifecycle scripts disabled. Upstream statically imports its Google Maps optional dependency even when its plugin is off, so that dependency must be present. Build upstream `sharp` explicitly if needed. Use an existing headless browser via `PUPPETEER_BROWSER_PATH`; do not install an app or run a web service for refresh.
4. Invoke the upstream local CLI `node source/app/action/index.mjs` with these input environment values: `USER=viggomeesters`, `BASE=metadata`, `REPOSITORIES=100`, `REPOSITORIES_FORKS=yes`, `REPOSITORIES_AFFILIATIONS=owner`, `PLUGIN_LANGUAGES=yes`, `PLUGIN_LANGUAGES_LIMIT=5`, `PLUGIN_ISOCALENDAR=yes`, `PLUGIN_ISOCALENDAR_DURATION=full-year`, `CONFIG_TIMEZONE=Europe/Amsterdam`, `CONFIG_DISPLAY=large`, `CONFIG_ANIMATIONS=no`, `OUTPUT_ACTION=none`, `USE_PREBUILT_IMAGE=no`, `USE_MOCKED_DATA=no`, `DEBUG=no`, `DEBUG_PRINT=no`, `CLEAN_WORKFLOWS=no`, `RETRIES=1`, `RETRIES_DELAY=0`. Prefix every input name with `INPUT_`.
5. Supply existing GitHub authentication only in the process environment as `INPUT_TOKEN`, never in a file, command log or repository. Do not create a new token or broaden scopes. Keep debug output disabled. Point `INPUT_FILENAME` at an explicit temporary destination relative to the upstream CLI's `/renders` output root. A `../` path can target an existing isolated temporary directory without creating `/renders`.
6. Verify that the output is valid SVG, has no plugin errors, private information or credentials, and renders correctly. Replace `assets/metrics.svg`, update the visible snapshot date and this provenance, then review the diff through an Issue and PR. Run the local output and render checks; do not add GitHub Actions.

Changes to this profile are Markdown and existing image assets. No new executable helper code is shipped; the patch records only the necessary privacy adaptation of the existing upstream renderer.
