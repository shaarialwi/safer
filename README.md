# SafePoint — disaster shelter finder

Buildless HTML, CSS and JavaScript for GitHub Pages. Open index.html to explore; host over HTTPS for geolocation. No API key or build step is needed. Google Maps opens externally; the embedded map is OpenStreetMap.

## Publish on GitHub Pages
1. Create a repository named `safepoint` at https://github.com/new.
2. Upload the contents of this folder, with `index.html` at the repository root, and commit to `main`.
3. In Settings → Pages, choose Deploy from a branch, `main`, `/ (root)`, then Save.
4. Once GitHub confirms deployment, visit https://shaarialwi.github.io/safepoint/ (assuming that owner and repository name).

## Included behaviour
- GPS or manual coordinates; straight-line distance sorting (not routing distance).
- Flood, fire and earthquake filters, text search and reported step-free access filter.
- Explicitly fictional demo; navigation to demo records is disabled.
- Local JSON dataset import with coordinate, duplicate ID, hazard, status, size and timestamp validation.
- Directions enabled only for imported open records with non-future verification and unexpired validity.
- Source and verification dates visible; data claims are not authenticated by this static prototype.
- Driving/walking Google Maps handoff with a route warning and explicit confirmation.
- No GPS storage or server upload by SafePoint. Opening Google Maps sends starting and destination coordinates to Google. Embedded maps use external network requests.
- Imported records live only in memory. Reloading clears them. No background alerts, live hazard feed, reservations or offline map support.

## Data format
`template.json` contains an intentionally expired, closed illustrative record. Replace every placeholder and coordinate with authority-approved information. ISO dates should include a timezone. `status` accepts open, closed, full, unknown; `hazards` accepts flood, fire, earthquake. `accessible` is a boolean.

Never mark a record open or extend validity without confirmation from its responsible authority. A building's existence does not establish it as a designated shelter. Suitability must be specific to the incident type. Client-side validation does not establish authority or authenticity.

## Before operational deployment
Obtain an authorised shelter registry and incident-specific approval, named data owners, freshness rules, capacity/closure updates and authenticated publishing. Add monitored authoritative feeds and a secure backend for operator changes. Assess routes against live incident zones and closures with emergency responders. Google Maps alone cannot certify evacuation routes. Conduct accessibility, field, connectivity and emergency-management acceptance testing.

## Verification
JavaScript syntax and core validation/distance/eligibility tests passed. GPS permission prompts, remote map loading and Google Maps handoff require browser/device verification; these were not exercised in this environment.

## References
- Google Maps URLs: https://developers.google.com/maps/documentation/urls/get-started
- Malaysia emergency line: https://www.malaysia.gov.my/en/categories/safety-and-community/public-safety/mers-999-emergency-line
- NADMA: https://www.nadma.gov.my/
- MET Malaysia: https://www.met.gov.my/
- Public InfoBanjir: https://publicinfobanjir.water.gov.my/
