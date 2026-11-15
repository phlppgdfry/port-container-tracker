# Validation evidence

Validation date: 15 November 2026. Fixtures represent June 2026 and are intentionally frozen. No historical business outcomes are inferred from this validation.

## Recorded local result

Python 3.15.2: **19 tests passed**. Chromium: **8 tests passed**. JavaScript syntax checks and Python compilation passed. The report command reproduced the committed synthetic baseline.

## Automated checks

- `make check`: Python unit/integration tests, HTTP round trips, invalid input, read/export round trip, durable state, stale-write rejection, simultaneous updates and audit-failure rollback; Python compilation; JavaScript syntax checks.
- `npm run test:e2e`: eight Chromium tests covering served brand assets, filters/empty state, responsive layouts at 390/768/1440 px, the domain workflow with reload persistence, and the public showcase.
- `make report`: baseline JSON and CSV generated from the same domain calculations used by the browser.

Domain coverage: Known ISO check digit, invalid identifiers, held release, clearance reason, full state machine, exact dwell boundary and departed dwell.

## Browser review

The Browser plugin is not available in this environment, so the final review uses the repository Playwright suite and the shared Playwright browser. The core flow was exercised through real forms and buttons against the local Python server. Reload persistence, visible success and rejection messages, record selection and mobile document width were checked. Screenshots are actual rendered pages, not design mockups.

1. Select MSCU1000017 and try to release it. The active customs hold blocks the transition.
2. Enter a fictional customs clearance reference, clear the hold, release the container, then record gate out.
3. Reload and select the same identifier. Its completed journey and frozen dwell remain available; inspect the activity log.

See [desktop screenshot](preview.png), [mobile screenshot](mobile.png), and the current [GitHub Actions run](https://github.com/phlppgdfry/port-container-tracker/actions/workflows/demo.yml). The badge reports the remote result; this document describes the checks, not an invented production certification.

## Final release checks

The final pass adds regression coverage for negative numeric CSV values, formula-leading text and a failed snapshot refresh after a version conflict. The conflict error remains visible, form inputs survive and controls are re-enabled without a script error. The versioned release is linked from the public setup section.

## Limits of the evidence

The suite tests a local single-workspace product with synthetic records. It does not establish external integration reliability, real user outcomes, scale, production security, legal compliance or clinical validity. No terminal operating system, EDI endpoint, AIS/vessel feed, real customs clearance or Oracle warehouse is connected. Clearing a hold is a simulation action in one trusted local workspace.
