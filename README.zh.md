# tlyboy

▲ tlyboy —— 管理 AI 写出来的产物

> [English](./README.md) | 简体中文

## 安装

macOS 与 Linux：

```bash
curl -fsSL https://tlyboy.com/install.sh | sh
```

脚本会自动选对平台的二进制、用 `SHA256SUMS.txt` 校验，然后装到 `~/.local/bin/tlyboy`。想换目录设 `TLYBOY_INSTALL_DIR`，想装指定版本设 `TLYBOY_VERSION`。

Windows（PowerShell）：

```powershell
irm https://tlyboy.com/install.ps1 | iex
```

同样的机制 —— 装到 `~\.local\bin\tlyboy.exe`，并把该目录加进用户 `PATH`。

macOS 的二进制经过 Developer ID 签名与公证，直接就能跑。

## 使用说明

### 登录

```bash
tlyboy login
```

会打开浏览器让你授权这台机器，然后把凭据存到 `~/.config/tlyboy/credentials.json`。

### 推送产物

Markdown 文档、mermaid 思维导图、待办清单都是同一条命令 —— 类型和标题从文件里推断：

```bash
tlyboy artifact push 周报.md -p 产品
```

### 其余命令

```bash
tlyboy artifact ls [-p <项目>]      # 列表，--trashed 看回收站
tlyboy artifact get <id>            # 把正文打到标准输出
tlyboy artifact rm <id>             # 进回收站，--purge 才是真删
tlyboy artifact restore <id>

tlyboy project ls
tlyboy project new <名字>
tlyboy project rename <id|名字> <新名字>
tlyboy project rm <id|名字>
tlyboy project restore <id|名字>
```

`rm` 是挪进回收站而不是销毁，而且删之前一定先问一句。在管道或 CI 里没法问，它就直接拒绝而不是替你猜；真要删加 `--yes`。

## 使用许可

[MIT](https://opensource.org/licenses/MIT) © tlyboy
