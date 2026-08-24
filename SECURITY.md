# Security Policy

## Reporting a vulnerability

Email **security@constly.com**. Please do not open a public issue for security
reports. Best-effort acknowledgment within 3 to 5 business days; critical issues
are prioritized ahead of feature work and pushed to every install through the
auto-updater.

Include reproduction steps and the affected version. Coordinated disclosure is
appreciated, and we will credit you in the release notes unless you would rather
we did not.

## Supported versions

The latest release always receives fixes. Older versions do not; the in-app
updater keeps installs current.

## Scope

Constly renders untrusted markdown inside a privileged webview, so the surfaces
worth a researcher's attention are HTML and SVG sanitization, the webview
content-security policy, link-scheme handling, the export child-process
invocation, and the updater trust chain. Reports that show a concrete path from
a malicious `.md` file to code execution, data exfiltration, or a bypassed
consent gate are especially welcome.
