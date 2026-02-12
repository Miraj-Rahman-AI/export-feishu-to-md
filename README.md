#fm

A CLI tool for converting Lark documents to Markdown. Runs directly as a single-file binary or npx file, requiring no complex configuration.

## Installation

#### Method 1: Run directly with npx (with Node.js environment)

No installation required, just use:

```bash
npx fm-ka export -d doxcnXXXXXXXXXX
npx fm-ka export -w V0gQw6yEZikjBAkKcrVcd8OlnYe
```

Alternatively, install globally:

```bash
npm i -g fm-ka
fm export -d doxcnXXXXXXXXXX
```

#### Method 2: Download Pre-compiled Binaries (No Runtime Required)

Download the files for your platform from [Releases](../../releases/latest):

```bash
# macOS Apple Silicon
sudo curl -Lo /usr/local/bin/fm https://github.com/WakeUp-Jin/export-feishu-to-md/releases/latest/download/fm-darwin-arm64 && sudo chmod +x /usr/local/bin/fm

# macOS Intel
sudo curl -Lo /usr/local/bin/fm https://github.com/WakeUp-Jin/export-feishu-to-md/releases/latest/download/fm-darwin-x64 && sudo chmod +x /usr/local/bin/fm

# Linux
sudo curl -Lo /usr/local/bin/fm https://github.com/WakeUp-Jin/export-feishu-to-md/releases/latest/download/fm-linux-x64 && sudo chmod +x /usr/local/bin/fm
```

Windows users can download `fm-windows-x64.exe` and place it in the PATH directory.

## Preliminary Preparations

1. Access [Feishu Open Platform](https://open.feishu.cn/app) to create an application.

2. Obtain the **App ID** and **App Secret**.

3. Grant permissions:

- `docx:document:readonly` - Read documents

- `drive:drive:readonly` - Download images/attachments

- `wiki:wiki:readonly` - Read the knowledge base (if you need to export knowledge base documents)

4. Publish the application and get it approved.

## Usage

```bash

# Set credentials (add to ~/.zshrc or ~/.bashrc for permanent effect)

export FEISHU_APP_ID=cli_xxxxxxxx

export FEISHU_APP_SECRET=xxxxxxxxxxxxxxxx

# Export cloud documents

fm export -d doxcnXXXXXXXXXX

fm export -d "https://your-company.feishu.cn/docx/doxcnXXXXXXXXXX"

# Export Knowledge Base Documentation

fm export -w V0gQw6yEZikjBAkKcrVcd8OlnYe

fm export -w "https://my.feishu.cn/wiki/V0gQw6yEZikjBAkKcrVcd8OlnYe"

# More Options

fm export -d <token> -o ./my-docs # Specify Output Directory

fm export -d <token> --no-images # Do not download images

fm export -d <token> --debug # Debug Logs

fm export -d <token> --app-id x --app-secret x # Send Credentials via Command Line

```

Output Example:

```
① Authentication Successful

② Parsing Knowledge Base Node: "Agent Evaluation" -> Mwa9dywpfomAmgxMVLzcNWpdnJq

③ Get Documentation: Agent Evaluation (131 blocks)

④ Markdown Conversion Completed

⑤ Download Media: 2/2 Completed

✔ Export Completed: output/AgentEvaluation.md

API Calls: 6 in total (auth:1, wiki:1, doc:1, blocks:1, media:2)

```

## Build from Source Code

```bash

# Requires Bun (https://bun.sh)

bun install

bun run build # Compile for the current platform -> dist/fm

bun run build:all # Compile for all platforms

```

## Release

Tag and push. GitHub Actions automatically compiles Release + publishes. npm:

```bash

git tag v0.1.0

git push origin v0.1.0

```

> Need to add in repository Settings -> Secrets `NPM_TOKEN`.

## Contributions

Issues and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License

[MIT](LICENSE)
