<!--
Repository preparation item from the wakecap-mobile-platform axis vision
("Repository preparation" section, [proposal]). This template mirrors the
quality gates AGENTS.md already commits every change to (see AGENTS.md
"Quality gates").
-->

## What and why

<!-- One or two sentences: what changed, why. -->

## Quality gates

Every one of these must pass before requesting review (run in this order,
per AGENTS.md "Quality gates"):

- [ ] `npm run lint` (`expo lint`) — no errors.
- [ ] `npm run typecheck` (`tsc --noEmit`) — no errors.
- [ ] Token scan: no hex color literal (`#[0-9a-fA-F]{3,8}`) outside `src/theme/` (`contracts/design-tokens.md`).
- [ ] Auth contract check: no direct IDS4 endpoint call outside `src/auth/`, no client secret literal anywhere (`contracts/auth.md` — PKCE public client).
- [ ] Instrumentation check: every new screen calls `useScreenTracking`; every new network/auth call wraps `startSpan`/`reportError` (`contracts/observability.md`; verified by reading the diff, no automated check yet).

There is no test command in this template yet — do not add one unless the
change was explicitly asked to add test infra (see AGENTS.md "What's
intentionally not in this template").

## Screenshots / trace evidence

<!-- For a UI change: before/after screenshot. For an observability change:
     the Grafana/Loki/Tempo query result showing the new trace or error. -->

## Related

<!-- Linear issue, blocker card path, or contract doc this PR implements. -->
