# Security policy

Report vulnerabilities in Desktop Accounting API, its SDKs or its examples privately. Do not open a public issue.

- Use GitHub's **Report a vulnerability** button on the affected repository's Security tab, or
- contact us through https://www.desktopaccountingapi.com/contact and ask for a private security channel. Do not include exploit details in the first message.

Include the affected repository and version, a description of the impact, and steps to reproduce. Never include real secret keys, webhook signing secrets, Web Connector passwords or customer data. Use test credentials or redact them.

If a secret key (`sk_live_...` or `sk_test_...`) may have been exposed, revoke it in the dashboard immediately. Keys can be revoked and replaced at any time.
