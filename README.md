# empeo Performance Hub — Gofive Product Owner Prototype

An interactive, orange-themed, single-page Performance Management prototype for the Gofive Product Owner exam. **All employee data is fictional.** This is a frontend-only demo with no backend or real authentication.

## Live demo

After GitHub Pages is enabled, the site will be available at:
https://3fe0d0.github.io/empeo-performance-management/

## How to use

Open `index.html` in a browser, or open the live GitHub Pages site. Use the top-right role selector. The browser saves demo changes to `localStorage`. Use **Reset demo** to restore sample data.

### Suggested end-to-end walkthrough

1. **HR Admin:** Review the six-person cycle, completed/pending reviews, rating distribution, shared 1–5 rubric, deadline, and publishing controls. Publishing is blocked until every review is submitted.
2. **Manager · Alex:** Select Ava Patel; review goals and submit a 1–5 rating supported by at least 20 characters of performance evidence.
3. **Manager · Jordan:** Select Oliver Reed and submit a rating and evidence.
4. **HR Admin:** Observe full completion; publish results. You can also try extending the deadline and triggering a **demo** reminder (no real message is sent).
5. **Employee:** Switch to Maya or Noah and see the published review. Reset the demo to confirm that reviews are hidden from employees before publishing.

## Why these features are in v1

- **Shared rating rubric (1–5):** gives managers common definitions.
- **Evidence-based evaluations:** encourages explainable, reviewable decisions.
- **Goal tracking:** helps employees and managers see ongoing progress.
- **HR oversight and rating distribution:** shows the review status and provides context for examining differences.
- **Deadline handling:** supports a missed cycle deadline with an extension and simulated reminders.
- **Publish gate:** prevents employees from seeing provisional scores before HR releases results.

This prototype does **not** automatically rank employees, assume that equal ratings prove fairness, or apply a forced bell curve. Different roles, goals, and circumstances need contextual evaluation.

## Deliberately excluded from v1

- **Cross-team calibration:** proposed requirement change for Part 2; not yet implemented in the demo.
- Real identity/authorization, SSO, secure backend database/API, persistent multi-user collaboration, audit logging, actual notifications, integrations, and advanced analytics.

## Handling the Part 2 calibration requirement

Proposed workflow: `review_open → calibration_open → calibration_locked → published`.

Managers compare ratings and evidence across teams and document adjustments. Keep original and calibrated ratings distinct, with reasons for adjustments. HR cannot publish until calibration is locked, and employees see **only final, published** scores.

Suggested measures: on-time review completion, time to calibrate, adjustment rates by team, cross-manager differences for comparable evidence, employee appeals, and perceived fairness.

## Scope / security notice

This is a **prototype**, not a production-ready HR system. Role switching is illustrative (not access control) and `localStorage` is not suitable for confidential employee data. Only fictional sample data is included.

## GitHub Pages setup

Repository **Settings → Pages → Build and deployment → Deploy from a branch → main → / (root) → Save**. Verify the actual deployed URL and test the end-to-end flow before submitting it to Gofive.
