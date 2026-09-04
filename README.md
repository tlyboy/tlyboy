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
tlyboy artifact push report.md -p Product
```

### Everything else

```bash
tlyboy artifact ls [-p <project>]      # list, --trashed for the recycle bin
tlyboy artifact get <id>               # print the body to stdout
tlyboy artifact rm <id>                # to the recycle bin, --purge to destroy
tlyboy artifact restore <id>

tlyboy project ls
tlyboy project new <name>
tlyboy project rename <id|name> <new-name>
tlyboy project rm <id|name>
tlyboy project restore <id|name>
```

`rm` moves things to a recycle bin rather than destroying them, and asks before it does. In a pipe or a CI job — nowhere to ask — it refuses instead of guessing; pass `--yes` when you mean it.

## License

[MIT](https://opensource.org/licenses/MIT) © tlyboy
