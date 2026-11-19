# `@cloudflare/test-harness`

Runs a project's Build Output in tests.

```ts
import { createTestHarness } from "@cloudflare/test-harness";
import { bindings } from "cf/config";

const harness = createTestHarness({
	workers: [
		// The project directory containing the build's `.cloudflare/output`
		{ projectDir: "./", envOverrides: { API_TOKEN: bindings.text("test") } },
	],
});

await harness.listen();
const response = await harness.fetch("/");

await harness.close();
```

See [`fixtures/create-test-harness-example`](https://github.com/cloudflare/workers-sdk/tree/main/fixtures/create-test-harness-example) for a complete example with Vitest and Playwright.

This package is experimental and its API may change in minor versions.
