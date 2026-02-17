# Contributing

Thank you for your interest in this project! We welcome your Issue and Pull Request submissions.

## Development Environment

- [Bun](https://bun.sh) >= 1.0

- TypeScript

```bash
git clone https://github.com/WakeUp-Jin/export-feishu-to-md.git

cd export-feishu-to-md

bun install

```

## Development Workflow

1. Fork this repository

2. Create your branch: `git checkout -b feat/your-feature`

3. Develop and test: `bun run dev -- export -d <token>`

4. Commit: `git commit -m "feat: add your feature"`

5. Push: `git push origin feat/your-feature`

6. Create a Pull Request

## Commit Specifications

Use [Conventional Commits](https://www.conventionalcommits.org/) format:

- `feat:` New feature

- `fix:` Fixes

- `docs:` Documentation

- `refactor:` Refactoring

- `chore:` Build/Tools

## Directory Structure

```
src/

index.ts # CLI entry point

config.ts # Configuration parsing

api/ # Lark API calls

auth.ts # Authentication

document.ts # Documentation/Wiki API

media.ts # Media download

counter.ts # API call count

converter/ # Markdown conversion

markdown.ts # Core renderer

types.ts # Type definitions

buffer.ts # String concatenation tool

emoji.ts # Emoji mapping

utils/

logger.ts # Logger

file.ts # File operations

```

## Submit an Issue

- Bugs: Please attach error logs (output in `--debug` mode)

- Features: Please describe the use case
