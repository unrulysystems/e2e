# e2e

Native E2E tooling experiments for React Native apps and games.

This repository is a reserved public shell. It does not yet contain migrated production code.

## Intended Scope

- Native device verification patterns for React Native apps
- Playwright-style driver experiments for real devices and simulators
- View tree, touch, screenshot, lifecycle, and rendering assertions
- Game-focused E2E helpers that preserve real runtime behavior

## Non-Goals

- Replacing the existing rn-playwright-driver repository before package boundaries are agreed
- Treating mocked or unit-only coverage as final verification for native runtime behavior
- Baking Sortessori-specific assumptions into general driver packages