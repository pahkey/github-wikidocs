# AGENTS.md

Guidelines for AI coding agents working in this repository.

## Project Overview

A **documentation repository** syncing with [WikiDocs](https://wikidocs.net). Markdown files are automatically published when pushed to the main branch.

**Repository**: https://github.com/pahkey/github-wikidocs

## Project Structure

```
github-wikidocs/
├── README.md       # Usage instructions
├── TOC.md          # Table of Contents (defines page hierarchy)
├── AGENTS.md       # This file
├── pages/          # Documentation pages (*.md)
└── assets/         # Images and static assets
```

## Build/Lint/Test Commands

**No build, lint, or test commands** - this is a documentation-only repository.

| Task | Command |
|------|---------|
| Validate | Use editor markdown preview |
| Preview | Push to GitHub, check WikiDocs |
| Publish | `git push origin main` (auto-syncs) |

## File Naming Conventions

### Pages (`pages/` directory)

- Use **numbered prefixes**: `01-`, `02-`, `01-1-`, `01-2-`
- Use **kebab-case**: `01-getting-started.md`
- Match title numbers: `# 01. 시작하기`

```
pages/01-getting-started.md  → # 01. 시작하기
pages/01-1-install.md        → # 01-1. 설치
pages/02-basics.md           → # 02. 기본 문법
```

### Assets (`assets/` directory)

- Use descriptive names: `diagram-workflow.png`, `screenshot-login.png`
- Reference with relative paths: `![설명](./assets/image.png)`

## Markdown Style Guidelines

### Headings

- One `#` (H1) per page as the title
- `##` for major sections, `###` for subsections
- Never skip heading levels

### Lists

- Use `-` for unordered lists (not `*`)
- Use `1.` for ordered lists
- 2-space indentation for nesting

### Code Blocks

Always specify language for syntax highlighting:

````markdown
```python
print("Hello, World!")
```
````

### Links and Images

```markdown
[페이지 제목](pages/01-getting-started.md)  # Internal
[WikiDocs](https://wikidocs.net)            # External
![이미지 설명](./assets/example.png)         # Image
```

## TOC.md Structure

Defines table of contents for WikiDocs. **All pages must be listed here.**

```markdown
# 목차

* [01. 시작하기](pages/01-getting-started.md)
  * [01-1. 설치](pages/01-1-install.md)
  * [01-2. 환경설정](pages/01-2-config.md)
* [02. 기본 문법](pages/02-basics.md)
```

**Rules:**
1. Use `*` for list items (WikiDocs requirement)
2. 2-space indentation for hierarchy
3. Titles must match page H1 headings exactly

## Content Guidelines

### Language

- Primary: **Korean (한국어)**
- Technical terms may use English
- Use formal polite speech (합니다체)

### Adding New Content

1. Create Markdown file in `pages/` with proper numbering
2. Add entry to `TOC.md` in correct position
3. Commit with descriptive message
4. Push to main branch

## Commit Messages

Use conventional commits format:

```
docs: add installation guide
docs: update getting started section
fix: correct broken image link
chore: reorganize assets folder
```

## Common Workflows

### Add a New Page

```bash
# 1. Create page: pages/02-new-topic.md with "# 02. 새로운 주제"
# 2. Add to TOC.md: * [02. 새로운 주제](pages/02-new-topic.md)
# 3. Commit and push
git add .
git commit -m "docs: add new topic section"
git push origin main
```

### Add an Image

```bash
# 1. Save image to assets/screenshot-feature.png
# 2. Reference in markdown: ![기능 스크린샷](./assets/screenshot-feature.png)
```

## Important Notes

1. **Auto Sync**: Push to `main` triggers WikiDocs sync
2. **Page Order**: WikiDocs sorts alphabetically - use numbered prefixes
3. **No Build Step**: Pure documentation, no build process
4. **TOC Required**: Pages not in `TOC.md` won't appear on WikiDocs
