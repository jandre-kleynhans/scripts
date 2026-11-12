# scripts

Small personal scripts.

## md

Live-preview a Markdown file in the browser as GitHub Flavoured Markdown, with GitHub's styling. The page updates whenever you save the file.

Raw HTML is rendered along with the Markdown, including Markdown written inside HTML blocks (for example a heading in a `<div>`).

### Install

```bash
git clone https://github.com/jandre-kleynhans/scripts.git
mkdir -p ~/.local/bin
cp scripts/md-preview/md ~/.local/bin/md
chmod +x ~/.local/bin/md
```

Make sure `~/.local/bin` is on your `PATH`. Python 3 is the only requirement.

On first run, `md` downloads a few pinned assets (the Markdown parser, GitHub's CSS, and syntax highlighting) into `~/.cache/md-preview/`. If you run the script from this repository, it uses the copies already in `md-preview/assets/` instead.

### Usage

```bash
md notes.md
```

This starts a local server and opens your browser. Press Ctrl+C to stop.

```bash
md --port 8123 notes.md
md --no-open notes.md
md --version
```

The preview is always light, so colours in your HTML stay as you wrote them, even when the Mac is in Dark Mode.

Links to other pages in the same folder (Markdown or HTML) open in this preview. Use the browser's back button, or a link, to go back. Images and other files in the folder are served as themselves.
