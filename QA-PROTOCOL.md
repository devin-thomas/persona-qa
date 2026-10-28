# Evidence protocol

Read this alongside the selected identity. Keep the persona's point of view;
these rules make its observations useful to a Judge across products and harnesses.
The task's explicit scope, model, effort, safety boundaries and budgets override
the roster's suggested defaults.

## Before testing

- Record the build/URL, environment, starting fixture state, browser/device
  simulation and the critical journey you intend to complete. Use synthetic data.
- Distinguish available features from disconnected or simulated services. A
  fixture without authentication does not demonstrate an authentication bypass.
- Start from the UI. Inspect the current labels, roles, control types, counts and
  visibility before automating. Use source inspection only when authorized, and
  label conclusions derived from source separately from observed behavior.
- Before checking individual controls, map the actions in the assigned journey:
  starting state, persistent effect, resulting state and the user's reason to
  choose each action. Compare actions that reach the same result. Challenge
  redundant controls, unnecessary decisions and labels that imply a distinction
  the product does not actually preserve. Passing tests or matching a spec does
  not establish that a control is useful. Respect deliberate shortcuts and
  safeguards when their different purpose is demonstrated.
- Reserve time for the report. A deadline is a bound, not permission to claim
  unfinished checks passed. Do not delegate, change models, use paid fallbacks,
  alter permissions, or publish unless the task authorizes that action.

## During testing

- Capture the exact record identity or URL as well as its visible name. A
  screenshot of another record is not evidence for the claimed record.
- Use the real control: a select option is not a button. Conditional fields must
  first be revealed through the relevant choice. Inspect a failed locator before
  retrying; record automation failures separately from product failures.
- Register explicit native-dialog handlers before triggering confirmations.
  Record dialog text and whether you accepted or dismissed it. Browser automation
  may dismiss dialogs automatically; retained data after dismissal is expected.
- Observe feedback immediately after each action. A later successful action may
  replace a previous error. Check the current live/status region, not only alerts.
- Compare before and after states using a discriminating fixture. A pre-existing
  success state, identical upload contents, or an already-reviewed record cannot
  prove that the action caused a change.
- Walk the ordinary task with empty, populated and unsaved states where relevant.
  Explain whether each control still makes sense in those states, including
  what the user would reasonably expect to be saved, discarded or kept separate.
- Trace the boundary under test: direct SDK calls may omit the application's
  authentication, authorization or request-validation wrapper. State what the
  harness replaces. A memory adapter does not verify SQL insert constraints or
  database-generated defaults; test those separately before making persistence
  claims. A caught exception is a failed or inconclusive check, never a successful
  return value.
- For persistence, reload or use a fresh context and verify the same saved record.
  For retries, compare stable identities, contents and counts before and after.
  Do not infer idempotency from one request or a cleared form alone.
- Keep screenshots, concise DOM/network evidence and scripts inside the assigned
  artifact folder. Stay within screenshot/output/time limits. Exclude credentials,
  cookies and private browser connection capabilities from reports and images.
- Machine-readable artifact fields contain exact existing paths only. Put event
  names, line numbers and explanatory parentheses in the observation text, not in
  `evidencePaths` or `screenshot`. Use the schema's empty/null representation when
  no screenshot exists, not a prose string such as "none (network only)".

## Classify observations

Each candidate must be one of:

- **Defect:** observed behavior conflicts with an explicit requirement, a visible
  promise, or a demonstrated usability/accessibility need. State that basis.
- **Suggestion:** an optional feature or preference. Missing bulk actions,
  shortcuts, real-time sync or a dashboard is not automatically a defect.
- **Coverage gap:** an untested, blocked or inconclusive check. Give the blocking
  condition and the smallest next observation that would resolve it.

State steps, expected/actual results, environment, evidence paths and confidence.
Severity reflects demonstrated impact, not persona enthusiasm. Do not equate
missing ARIA attributes with failure when native semantics already work; explain
the user task that is affected. Do not claim screen-reader, security, retention,
accessibility conformance or real-provider behavior from a simulation alone.

## Report completion honestly

Include these alongside the identity's domain-specific report format. If the task
provides a schema, map them into its corresponding fields rather than changing it.

- Journey status: `completed`, `partial`, `blocked` or `inconclusive`.
- Actions actually performed, meaningful first success, and checks not completed.
- Findings separated into defects, suggestions and coverage gaps, with confidence
  and exact evidence. Empty findings are valid; do not invent an issue quota.
- Measured elapsed time and its start/end boundary, or `unknown`. Never substitute
  zero or an estimate for an unmeasured first-success time.
- Fixture limitations, simulations, denied tools, repaired locators, dialog
  decisions and any evidence-to-narrative discrepancy.

A browser opening or preview loading is not persisted first success. A valid
report and a successful process exit do not imply every checklist item passed.

## Judge rules

The Judge consolidates evidence; it does not become another tester. Account for
every candidate as accepted, duplicate, deferred or rejected, with reasons. Check
requirements before accepting feature requests as bugs. Preserve distinct scopes
and build versions instead of presenting mixed runs as one comprehensive pass.

Challenge thin or conflicting evidence with a narrow re-test on the requested
harness/model. Label any supplied diagnostic hints as assisted reproduction and
preserve the original report. Audit record identity, dialog decisions, baseline
state and timing boundaries. Prioritize actual loss, privacy exposure, task
blockers and accessibility barriers; distinguish a helpful label improvement
from an unverified conformance claim. Give owners and concrete re-test criteria.
