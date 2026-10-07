# Desktop Accounting API

A REST API and typed SDKs for QuickBooks Desktop and QuickBooks Enterprise. Your application calls one HTTPS API, and Desktop Accounting API delivers each request to your customer's company file through the QuickBooks Web Connector.

[Website](https://www.desktopaccountingapi.com) · [Documentation](https://www.desktopaccountingapi.com/docs/) · [API reference](https://www.desktopaccountingapi.com/docs/api/reference/) · [Status](https://status.desktopaccountingapi.com) · [Pricing](https://www.desktopaccountingapi.com/pricing) · [Contact](https://www.desktopaccountingapi.com/contact)

## Packages

All five packages are generated from the same API contract and released together with the same version (currently **0.2.1**).

| Language | Repository | Install |
| --- | --- | --- |
| Node.js, TypeScript | [quickbooks-desktop-node](https://github.com/DesktopAccountingAPI/quickbooks-desktop-node) | [`npm install @desktopaccountingapi/quickbooks-desktop`](https://www.npmjs.com/package/@desktopaccountingapi/quickbooks-desktop) |
| Python | [quickbooks-desktop-python](https://github.com/DesktopAccountingAPI/quickbooks-desktop-python) | [`pip install desktopaccountingapi-quickbooks-desktop`](https://pypi.org/project/desktopaccountingapi-quickbooks-desktop/) |
| C# / .NET | [quickbooks-desktop-dotnet](https://github.com/DesktopAccountingAPI/quickbooks-desktop-dotnet) | [`dotnet add package DesktopAccountingAPI.QuickBooksDesktop`](https://www.nuget.org/packages/DesktopAccountingAPI.QuickBooksDesktop) |
| Java | [quickbooks-desktop-java](https://github.com/DesktopAccountingAPI/quickbooks-desktop-java) | [`com.desktopaccountingapi:quickbooks-desktop`](https://central.sonatype.com/artifact/com.desktopaccountingapi/quickbooks-desktop) |
| MCP server for AI tools | [quickbooks-desktop-mcp](https://github.com/DesktopAccountingAPI/quickbooks-desktop-mcp) | [`npx -y @desktopaccountingapi/quickbooks-desktop-mcp`](https://www.npmjs.com/package/@desktopaccountingapi/quickbooks-desktop-mcp) |

Runnable integrations for all four languages are in [examples](https://github.com/DesktopAccountingAPI/examples).

## What the SDKs share

- A resource tree that mirrors the API: `client.qbd.invoices.list()`, `client.endUsers.create()`, `client.requests.retrieve()`.
- Auto-pagination that requests the next page only when your loop needs it and reads ahead for slow loops. When a QuickBooks cursor expires, the SDK raises a typed error with your progress and never restarts the query silently.
- Typed errors keyed on the API's error `type` and `code`, with `userFacingMessage`, `fixes`, `docsUrl` and `requestId` on every error.
- Retries only where they are safe. Every write carries an idempotency key that is reused across its retries, and a write whose outcome is unknown is never retried.
- Exact money: decimal types in every language instead of floating point.
- Async requests with request handles, and Standard Webhooks signature verification.

## Support

Questions about your account, keys, billing or a connection: [contact us](https://www.desktopaccountingapi.com/contact). Bugs in an SDK: open an issue in its repository. Security reports: use **Report a vulnerability** on the affected repository.

---

QuickBooks is a registered trademark of Intuit Inc. Desktop Accounting API is an independent product and is not affiliated with, endorsed by, or approved by Intuit Inc.
