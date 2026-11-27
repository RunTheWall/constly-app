# Security Policy

## Reporting a vulnerability

Email **security@constly.com**. Please do not open a public issue for a security
report.

Include the steps to reproduce it and the version you tested. We aim to:

- acknowledge your report within 3 business days;
- tell you within 7 days whether we can confirm it.

Coordinated disclosure is appreciated. We credit you in the release notes unless
you would rather we did not.

## How fast we fix

These are targets, counted from the day we confirm an issue. They are not
guarantees.

| Severity | Target for a fixed release |
|---|---|
| Critical | 14 days |
| High | 30 days |
| Anything else | 45 days |

A flaw in a third-party library that Constly cannot reach is updated in the next
regular release once a fixed version can be used. It is listed under known open
advisories below until then.

When a new advisory is published for a library Constly ships, we aim to assess
it within 5 business days: whether Constly can reach the flaw, and what closes
it.

## How we find out

- The dependency audit runs on every pull request and on every push to the main
  branch, against the RustSec and npm advisory databases.
- Once a day, the same audit runs on the current source and on the lock files
  of the released version, and opens a tracked issue for anything new.
- GitHub's dependency alerts are on.
- Reports sent to security@constly.com.

## Supported versions

The latest release receives fixes. Older versions do not.

The in-app updater offers the latest release to every install that can run it.
A Mac whose macOS is older than a release needs is told so, and stays on the
version it has, which receives no further fixes.

## How updates reach you

- By default, Constly checks for an update when it starts and every 3 hours
  after that. It asks `downloads.constly.com` first, and a copy on GitHub if
  that does not answer. Both are https.
- No update is downloaded or installed until you choose to update.
- Every update is signed with Constly's update key (Ed25519, minisign), and the
  app checks the signature over the bytes it is about to install. The signature
  also names the version, and Constly installs an update only when that version
  is newer than the one running.
- You can turn the automatic check off, and an administrator can turn it off or
  point Constly at their own update feed by policy. A policy cannot switch off
  the signature check.
- The Linux tar build is told about an update and given a download link. It
  does not update in place.
- The macOS and Windows installers are code-signed, and the macOS builds are
  notarised by Apple. The Linux packages are not code-signed; each download on
  constly.com has a published SHA-256 checksum, and in-app updates to the deb
  and rpm packages are checked against the update key like every other update.

The signing identities, certificate details and the update key are listed at
<https://constly.com/security>.

## Software bill of materials

Starting with the release after 4.15.1, each release has a software bill of
materials in CycloneDX format, attached to the release as two files: one for
the Rust libraries and one for the JavaScript libraries. They are made from the
lock files, so they list every library locked for any platform, including ones
used only while building and ones a given installer does not contain. Nothing
is removed from the list. A note beside the files gives the counts per
platform.
The fonts and other bundled files are listed in the third-party notices inside
the app.

## Known open advisories

What `cargo audit` and `pnpm audit --prod` report as vulnerabilities against
the current release, in the libraries that are in a Constly installer, and why
each is still there.

| Advisory | Library | Does it affect Constly? | What closes it |
|---|---|---|---|
| RUSTSEC-2026-0194, RUSTSEC-2026-0195 | quick-xml 0.38.4 | No. This copy is used only by the citation parser inside the PDF engine, which Constly never calls, so no XML from a document reaches it. | The upstream citation library moving to quick-xml 0.41 or later. |
| RUSTSEC-2026-0594 | cookie 0.18.1 (in 4.15.1) | No. Only the library's private cookie jar is affected, and that feature is not compiled into Constly. | Already updated in source (cookie 0.18.3). It ships in the next release. |

The same tools print warnings for libraries that are unmaintained, unsound or
withdrawn. Two of those have GitHub advisory ids, so some scanners report them
as vulnerabilities:

| Advisory | Library | Does it affect Constly? | What closes it |
|---|---|---|---|
| RUSTSEC-2024-0429 (GHSA-wrw7-89jp-8q8g) | glib 0.18.5 (Linux only) | No. The advisory is about one iterator type, `VariantStrIter`. Nothing in Constly or in any library it is built from uses that type. | The Linux window toolkit bindings moving to glib 0.20 or later. |
| RUSTSEC-2026-0486 (GHSA-jh2m-fhpj-3vr7) | rustix 1.1.4 (in 4.15.1) | No. The advisory is about reading extended file attributes with an empty buffer. Constly only writes them, when it unpacks an archive. | Already updated in source (rustix 1.1.6). It ships in the next release. |

## Fixed vulnerabilities

Every advisory our records show a release closed, since 4.12.0, in the
libraries that are in a Constly installer. Libraries used only to build
Constly, and libraries that are locked but never built into it, are in no
installer and are not listed. The status is one of two:

- **Not affected.** We checked, and Constly did not use the affected part. The
  row says why. The library was updated anyway.
- **Fixed by update.** Closed by updating the library to a fixed version. This
  makes no statement about whether Constly was affected.

| Released | Version | Advisory | What changed | Status |
|---|---|---|---|---|
| 2026-11-24 | 4.15.1 | RUSTSEC-2026-0592 | url 2.5.8 to 2.5.9 | Not affected. Nothing in Constly was found to call the affected function. |
| 2026-11-06 | 4.14.1 | GHSA-w28w-mhc8-qvjv | Tauri updated to 2.12.5 | Not affected. Constly opens none of the channels involved, and using the flaw needs script already running in a Constly window, which the content-security policy and sanitizer are there to stop. |
| 2026-11-06 | 4.14.1 | GHSA-9g54-6x48-9vpw | tauri-plugin-fs, same update | Not affected. Constly does not load that plugin. |
| 2026-11-06 | 4.14.1 | RUSTSEC-2026-0367, -0368, -0369, -0429 | zip 4.6.1 removed | Not affected. Constly never called the affected functions, and the updater could only for a signed zip payload, which Constly's Windows update is not. |
| 2026-11-06 | 4.14.1 | RUSTSEC-2026-0545, -0548 | zip 4.6.1 removed | Fixed by update. |
| 2026-11-06 | 4.14.1 | RUSTSEC-2026-0433 | pulldown-cmark 0.13.5 to 0.13.6 | Not affected. Constly never sets the option involved. |
| 2026-11-01 | 4.13.0 | GHSA-cg2g-xh64-v4q7, GHSA-mrv2-3pqr-j5jr, GHSA-c6gr-qvv4-5v3f | DOMPurify 3.4.16 to 3.4.17 | Not affected. Constly sanitizes text only, and the three flaws are in the other mode. |
| 2026-11-01 | 4.13.0 | RUSTSEC-2026-0382, -0383 | rustls-webpki updated to 0.103.16 (Linux) | Fixed by update. |
| 2026-11-01 | 4.13.0 | RUSTSEC-2026-0414 | pulldown-cmark updated | Fixed by update. |
| 2026-10-20 | 4.12.0 | RUSTSEC-2026-0346 | rustls updated to 0.23.46 | Not affected. It needs a custom session store, and Constly has none. |
| 2026-10-20 | 4.12.0 | RUSTSEC-2026-0348 | rustls, same update | Not affected. It needs a compression feature that is not compiled in. |
| 2026-10-20 | 4.12.0 | RUSTSEC-2026-0347, -0349 | rustls, same update | Fixed by update. |

## Scope

Constly opens markdown files from anywhere, including files you did not write,
and shows them in a window that can also open and save your documents. Keeping
a file's content from doing anything but being displayed is the main job of
Constly's security design, so these are the places most worth a researcher's
attention: HTML and SVG sanitization, the content-security policy, how links
are handled, how export starts other programs, and the update trust chain.
Reports that show a concrete path from a crafted `.md` file to running code,
sending data out, or getting past a consent prompt are especially welcome.
