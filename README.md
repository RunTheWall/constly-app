<p align="center">
  <img src="assets/demo.gif" width="720" alt="Constly rendering markdown as you type: a heading, bold text, a task list, a quote, and a syntax-highlighted code block resolve in place while the raw marks melt away, and the editor shifts from light to dark.">
</p>

<h1 align="center">Constly</h1>

<p align="center">
  <b>A WYSIWYG markdown editor that renders the marks away as you type.</b><br>
  Local-first, private, plain <code>.md</code>. Native builds for macOS, Windows, and Linux.
</p>

<p align="center">
  <a href="https://constly.com/download"><img src="https://img.shields.io/badge/download-constly.com-4666d1?style=flat-square" alt="Download"></a>
  <img src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fdownloads.constly.com%2Flatest.json&query=%24.version&label=version&prefix=v&color=4666d1&style=flat-square" alt="Latest version">
  <img src="https://img.shields.io/badge/free%20to%20use-no%20account-4666d1?style=flat-square" alt="Free to use">
  <a href="https://github.com/RunTheWall/homebrew-tap"><img src="https://img.shields.io/badge/homebrew-runthewall%2Ftap-4666d1?style=flat-square&logo=homebrew&logoColor=white" alt="Homebrew tap"></a>
  <a href="https://github.com/RunTheWall/constly-app/stargazers"><img src="https://img.shields.io/github/stars/RunTheWall/constly-app?style=social" alt="Stars"></a>
</p>

<p align="center">
  <b>Runs on</b>
  <img src="https://img.shields.io/badge/macOS-000000?logo=apple&logoColor=white" alt="macOS">
  <img src="https://img.shields.io/badge/Windows%2010%2F11-0078D6?logo=windows&logoColor=white" alt="Windows">
  <img src="https://img.shields.io/badge/Linux-FCC624?logo=linux&logoColor=black" alt="Linux">
</p>

<p align="center">
  <a href="https://constly.com/download"><b>Download</b></a> &nbsp;·&nbsp;
  <a href="https://runthewall.github.io/constly-app/">Release notes</a> &nbsp;·&nbsp;
  <a href="ROADMAP.md">Roadmap</a> &nbsp;·&nbsp;
  <a href="https://constly.com/blog">Blog</a>
</p>

---

Type `# a heading`, `**bold**`, a table, a code fence, and each one renders in
place, the raw marks melting away as you go. Your file on disk stays plain
markdown, byte for byte. No web app in a wrapper, no proprietary format, no
account.

## Install

| Platform | How |
|---|---|
| **macOS** | [Download the DMG](https://constly.com/download) (Apple Silicon or Intel), or install with Homebrew (below) |
| **Windows** | [Download the installer](https://constly.com/download) (signed, 10 and 11, 64-bit) |
| **Linux** | [Download](https://constly.com/download) the `.deb`, `.rpm`, or tarball |

On macOS, install and stay current through Homebrew:

```sh
brew install --cask runthewall/tap/constly
```

Or tap first, then install:

```sh
brew tap runthewall/tap
brew install --cask constly
```

The cask points at the signed, notarized builds and uses Constly's own updater, so
it keeps itself current.

## Pricing

<p align="center">
  <img src="assets/pricing-pass.png" width="620" alt="Constly's pricing drawn as a boarding pass: Today, free with every feature and no catch; after two weeks, a gentle weekly reminder; anytime, pay once and it is yours forever. A one-time fare of $19.99, up to 3 devices, no subscription, no expiry, no lock-in.">
</p>

Constly is free to use for as long as you need. Every feature is unlocked, nothing
expires, and exports never carry a watermark. No account, no card. After two weeks
a gentle dialog asks you to buy, and that dialog is the whole business model.

To retire the reminder and back a tiny studio, a one-time license is **$19.99 USD**
(plus applicable tax). No subscription, ever, and one license covers every platform
you use. Need several seats? Volume licenses are available on request.

See the full details on [constly.com](https://constly.com/#pricing).

## This repository

Constly is a closed-source app: there is no source code here and no builds to
download in this repo. Every release lives on
[constly.com](https://constly.com/download), signed and notarized. This is the
community home, where you:

- **Report bugs and request features** in [Issues](https://github.com/RunTheWall/constly-app/issues/new/choose)
- **Follow the [roadmap](ROADMAP.md)** and upvote what matters to you
- **Read the [release notes](CHANGELOG.md)**, also browsable at [runthewall.github.io/constly-app](https://runthewall.github.io/constly-app/)

To report a security vulnerability, see the [security policy](SECURITY.md).

---

<p align="center">
  Built with care by <a href="https://github.com/RunTheWall">Run The Wall Pty Ltd</a>.<br>
  <a href="https://constly.com">constly.com</a>
</p>
