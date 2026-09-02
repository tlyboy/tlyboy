# tlyboy

▲ tlyboy — manage the artifacts your AI writes

> English | [简体中文](./README.zh.md)

## Install

macOS and Linux:

```bash
curl -fsSL https://tlyboy.com/install.sh | sh
```

It picks the right binary for your platform, checks it against `SHA256SUMS.txt`, and installs to `~/.local/bin/tlyboy`. Set `TLYBOY_INSTALL_DIR` to install elsewhere, or `TLYBOY_VERSION` to pin a version.

Windows (PowerShell):

```powershell
irm https://tlyboy.com/install.ps1 | iex
```

Same idea — it installs to `~\.local\bin\tlyboy.exe` and adds that directory to your user `PATH`.

The macOS binaries are signed with a Developer ID and notarized, so they run without any extra step.

## Usage

### Sign in

```bash
tlyboy login
```

Opens your browser so you can approve this machine, then stores the credential in `~/.config/tlyboy/credentials.json`.

### Push an artifact

Markdown documents, mermaid mind maps and task lists all go up the same way — the kind and the title are inferred from the file:

```bash
tlyboy push report.md -p Product
claude -p 'write the weekly report' | tlyboy push - -p Product --title 'Week 36'
```

## License

[MIT](https://opensource.org/licenses/MIT) © tlyboy
