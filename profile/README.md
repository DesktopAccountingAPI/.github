# Desktop Accounting API

A REST API and typed SDKs for QuickBooks Desktop and QuickBooks Enterprise. Your application calls one HTTPS API, and Desktop Accounting API delivers each request to your customer's company file through the QuickBooks Web Connector.

[Website](https://www.desktopaccountingapi.com) · [Documentation](https://www.desktopaccountingapi.com/docs/) · [Pricing](https://www.desktopaccountingapi.com/pricing) · [Contact](https://www.desktopaccountingapi.com/contact)

## SDKs

| Language | Repository | Package |
| --- | --- | --- |
| Node.js, TypeScript, JavaScript | [quickbooks-desktop-node](https://github.com/DesktopAccountingAPI/quickbooks-desktop-node) | `@desktopaccountingapi/quickbooks-desktop` |
| Python | [quickbooks-desktop-python](https://github.com/DesktopAccountingAPI/quickbooks-desktop-python) | `desktopaccountingapi-quickbooks-desktop` |
| C# / .NET | [quickbooks-desktop-dotnet](https://github.com/DesktopAccountingAPI/quickbooks-desktop-dotnet) | `DesktopAccountingAPI.QuickBooksDesktop` |
| Java | [quickbooks-desktop-java](https://github.com/DesktopAccountingAPI/quickbooks-desktop-java) | `com.desktopaccountingapi:quickbooks-desktop` |

Runnable integrations for all four languages are in [examples](https://github.com/DesktopAccountingAPI/examples).

All four SDKs are generated from the same OpenAPI contract as the API reference and share a hand-written runtime design:

- A resource tree that mirrors the API: `client.qbd.invoices.list()`, `client.endUsers.create()`, `client.requests.retrieve()`.
- Auto-pagination with one page of read-ahead. When a QuickBooks cursor expires, the SDK raises a typed error with your progress and never restarts the query silently.
- Typed errors keyed on the API's error `type` and `code`, with `userFacingMessage`, `fixes`, `docsUrl` and `requestId` on every error.
- Retries only where they are safe. Every write carries an idempotency key that is reused across its retries, and a write whose outcome is unknown is never retried.
- Exact money: decimal types in every language instead of floating point.
- Async requests with request handles, and Standard Webhooks signature verification.

---

QuickBooks is a registered trademark of Intuit Inc. Desktop Accounting API is an independent product and is not affiliated with, endorsed by, or approved by Intuit Inc.
