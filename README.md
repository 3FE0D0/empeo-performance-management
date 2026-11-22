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
5. **HR Admin (Fairness Review):** Compare rating distributions across teams, then use the two employee dropdowns to compare goal context and documented evidence. This does not adjust ratings or lock calibration.
6. **Employee:** Switch to Maya or Noah and see the published review. Reset the demo to confirm that reviews are hidden from employees before publishing.

## Why these features are in v1

- **Shared rating rubric (1–5):** gives managers common definitions.
- **Evidence-based evaluations:** encourages explainable, reviewable decisions.
- **Goal tracking:** helps employees and managers see ongoing progress.
- **HR oversight and rating distribution:** shows the review status and provides context for examining differences.
- **Cross-team Fairness Review (added):** compare Sales and Engineering rating patterns side-by-side; choose two submitted employees and inspect their goals, rating, and documented evidence. This is a contextual review aid, **not** automated bias detection or a locked calibration workflow.
- **Deadline handling:** supports a missed cycle deadline with an extension and simulated reminders.
- **Publish gate:** prevents employees from seeing provisional scores before HR releases results.

This prototype does **not** automatically rank employees, assume that equal ratings prove fairness, or apply a forced bell curve. Different roles, goals, and circumstances need contextual evaluation.

## Latest improvements (v1.2)

- **Fairness Review Considerations:** explains why differences in ratings require contextual review of goal difficulty, role expectations, and manager evidence, without falsely claiming to detect bias.
- **Provisional Performance Overview:** groups submitted ratings into 4–5 (High performance), 3 (Meets expectations), and 1–2 (Needs support). Pending reviews are excluded. The groups are screening aids rather than definitive judgments or calibrated results.
- **Review Workflow Status:** displays manager reviews, HR readiness, and results release. Formal cross-team calibration remains a proposed next step, not an implemented workflow.
- **Employee Comparison Validation:** prevents comparing the same employee in both columns.
- **Overdue Handling:** includes a **Simulate missed deadline** control and **Extend +7 days** action for the HR demo. Managers cannot submit or edit reviews after the deadline until HR extends it. Reminders remain simulated.

### Suggested extra acceptance checks

1. In HR Admin, confirm that Performance overview shows 2 High, 1 Meets, 1 Needs support with the initial 4 submitted reviews.
2. In Fairness Review, compare Maya and Noah. Check that changing a dropdown refreshes contextual guidance and that identical employee selections are blocked.
3. In HR Admin, select **Simulate missed deadline**. Switch to Manager: rating and review submission should be disabled.
4. Return to HR Admin and choose **Extend +7 days**. Manager submissions should be enabled again.
5. Submit Ava and Oliver reviews, check 6/6 completion and HR readiness, publish, and confirm employee visibility.
6. Select **Reset demo** for a clean walkthrough.

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
