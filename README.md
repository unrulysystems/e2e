# e2e

Native E2E tooling experiments for React Native apps and games.

This repository is a reserved public shell. It does not yet contain migrated production code.

## Intended Scope

- Native device verification patterns for React Native apps
- Playwright-style driver experiments for real devices and simulators
- View tree, touch, screenshot, lifecycle, and rendering assertions
- Game-focused E2E helpers that preserve real runtime behavior

## Migration Handoff

Sortessori is the reference app for the first native-game E2E evidence slice. The current
source of truth is `../sortessori/docs/unruly-systems-migration-plan.json`, backed by
`../sortessori/docs/webgpu-cutover-audit.md` and the physical walkthrough template at
`../sortessori/docs/heart-happy-iphone-walkthrough-2026-05-12.md`.

Import reusable E2E helpers here only after the Sortessori iOS WebGPU cutover has physical
manual evidence for touch, VoiceOver, sensory feedback, and Expo GL rollback, and
`../sortessori` passes:

```bash
bun run ci
bun run verify:webgpu-cutover
bun run verify:package-boundaries
```

The first eligible slice is the device-backed verification pattern, not Sortessori-specific
selectors, object labels, or gameplay assertions. Keep manual physical evidence explicit;
do not replace it with automated proxy signals.

## Non-Goals

- Replacing the existing rn-playwright-driver repository before package boundaries are agreed
- Treating mocked or unit-only coverage as final verification for native runtime behavior
- Baking Sortessori-specific assumptions into general driver packages
