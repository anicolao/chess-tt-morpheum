# E2E Testing Guide

All E2E tests in this project must adhere to the following strict guidelines to ensure reliability and performance.

## Structure
- Tests must enforce a clear E2E structure, verifying complete workflows and integrating systems seamlessly.
- Tests must be fully isolated and must not rely on state from previous tests.
- Always follow the Arrange-Act-Assert pattern.

## Prohibitions
- **No Timeouts > 2000ms**: There is a strict prohibition against timeouts of any kind exceeding 2000ms. Operations taking longer than this are considered performance failures.
- **No `waitForTimeout`**: There is a strict prohibition against using `waitForTimeout` in tests. Tests must rely on deterministic events (e.g., waiting for elements to appear, network requests to complete, or state changes) rather than arbitrary sleep durations.
