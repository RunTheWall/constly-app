# Constly release notes

What is new in each release of Constly. Download the latest at
[constly.com/download](https://constly.com/download).

## 4.8.0 (2026-09-21)

*Your documents, your pictures, your say.*

- **Images from anywhere, with one question.** An image that lives outside the
  document's folder, or on the web, gets a Load button in the editor and a
  review before a PDF or Word export. Constly asks once, in a system dialog
  that names the file, and remembers your answer until you quit. Anything you
  loaded is ticked when you export.
- **Word import brings its tables and pictures.** Tables arrive as tables,
  and the pictures come along, landing in a folder next to the file when you
  save it.
- **The caret lands where you click.** Under a stack of diagrams and equations,
  a click puts the cursor on the line you aimed at.
- **Updates show their progress.** A bar with megabytes while it downloads. If
  you keep working while it installs, Constly asks before restarting (Mac and
  Linux).
- **PDF export follows your code settings.** Dark code blocks and shell
  highlighting for unlabelled fences carry through to the PDF.
- **Pictures beside your document appear in the PDF.** An image the export
  cannot embed becomes a note in its place instead of stopping the export.
- **Export dialogs open in your document's folder.**
- A handful of smaller fixes and polish: a faster launch, crisper code
  comments in the dark theme, and a note when a web image could not be fetched.

## 4.7.1 (2026-09-06)

- **Fixed: the Settings window would not close.** In 4.7.0 its close button did
  nothing on every platform (maximize worked, which helped nobody). Quitting
  Constly was the way out; nothing was lost. Fixed, with a test so this class of
  bug fails the build instead of reaching you.

## 4.7.0 (2026-09-06)

*Constly meets your IDE.*

- **Open Markdown in Constly, straight from VS Code.** A new extension — also on
  [Open VSX](https://open-vsx.org/extension/constly/constly), where Cursor,
  Windsurf and VSCodium shop — hands the file you are looking at to Constly:
  saved if it needed saving, opened at the same line and column you were on.
  Look for *Constly: Open in Constly* in the editor title bar and the
  right-click menu. It opens several files at once too, from Finder, Explorer
  or the command line.
- **Update checks get through corporate networks** that inspect TLS, instead of
  quietly reporting "up to date" when a new version is waiting.
- **A rarer kind of start-up hiccup on Linux is fixed** — X11 sessions no longer
  lose a launch now and then.
- **A file that moves or is deleted out from under you now says so**, instead of
  being silently recreated when you save.

## 4.6.3 (2026-08-24)

- Reloading a file that changed outside Constly keeps your undo history, so a
  single undo brings your own version back.
- A handful of smaller fixes and polish.

## 4.6.2 (2026-07-11)

- Downloads and updates are about half the size. Constly now ships a build
  tuned for your Mac, Apple Silicon or Intel, and existing installs switch over
  on their own.

## 4.6.1 (2026-07-08)

- Long documents open fully rendered, with every table, diagram, math block,
  and table of contents in place from the first moment.
- Wide tables keep every column readable, and a table wider than the page
  scrolls sideways instead of squeezing.

## 4.6.0 (2026-07-06)

- Leave a table without reaching for the mouse: arrow out of the top or bottom
  row, or press Escape from any cell, to land on the line beside it.
- Command-click (Control-click on Windows and Linux) opens every kind of link,
  including bare URLs, www links, email addresses, and reference-style links, in
  every mode. Only http, https, and mailto targets open, always in your browser.

## 4.5.0 (2026-07-06)

- Export a PDF from inside Constly. It renders a self-contained,
  accessibility-tagged PDF that looks the same on every machine and works fully
  offline, with the same reading width you use in the editor. Prefer the system
  print dialog? It is one setting away.
- Imported web pages arrive as the article, with the navigation bars, cookie
  banners, and skip links left behind.
- Richer syntax highlighting across the board, shell commands especially. Two
  new options: render code on a dark panel under any theme, and treat an
  unlabeled code block as shell.

## 4.4.0 (2026-07-01)

- Print from inside Constly with a live preview: press the print shortcut and a
  real print panel opens, matching the page you see in the editor, with Save as
  PDF right there.
- Choose your reading width in Settings, Standard, Wide, or Wider, applied in
  both the editor and in print.

## 4.3.0 (2026-07-01)

- Each document opens in its own window, the feel where a window is a document.
  Prefer tabs? One setting puts it back.
- Everything returns exactly as you left it: quit with several windows open and
  relaunch to the same files, drafts, sizes, and positions.
- Inline markdown renders inside table cells, code, bold, italic, strikethrough,
  and links, revealing the raw text when you click in and formatting again when
  you click out.

## 4.2.2 (2026-06-29)

- Restart Constly and every tab comes back in order, the one you were on in
  focus and unsaved drafts intact.

## 4.2.0 (2026-06-29)

- The setup wizard ends on a boarding pass: your simple terms, free to use with
  an optional one-time license, drawn as a ticket with a plane tracing the route.
- Run the setup tour again any time from the Constly menu.
