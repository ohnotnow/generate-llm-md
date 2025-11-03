# Generate LLM Markdown

A PHP CLI tool that automatically generates a `.llm.md` file for your repository - a concise overview document designed to help LLMs quickly understand your codebase.

## What it does

This script analyzes your repository and creates a structured markdown file containing:

- **Purpose** - A summary of your project (from README.md)
- **Tech Stack** - Detected from composer.json and .lando.yml
- **Directory Structure** - A filtered tree view respecting .gitignore
- **Key Entry Points** - Main route files (web.php, api.php)
- **Features** - Extracted from your test files

## Requirements

- PHP 7.4+
- (Optional) OpenAI API key for enhanced summaries

## Usage

```bash
php generate-llm-md.php /path/to/your/repo
```

This will create a `.llm.md` file in the specified repository directory.

### With OpenAI Enhancement

For better feature filtering and README summarization, set your OpenAI API key:

```bash
export OPENAI_API_KEY="your-key-here"
php generate-llm-md.php /path/to/your/repo
```

Without the API key, the script will still work but will use simpler text extraction methods.

## Example Output

The generated `.llm.md` includes sections like:

```markdown
# Repository Overview

## Purpose
This application manages student projects...

## Tech Stack
Laravel 11.x, PHP 8.2, livewire

## Directory Structure
├── app
│   ├── Http
│   └── Models
├── routes
└── tests

## Key Entry Points
- routes/web.php

## Features (from tests)
- User can create a project
- Admin can export reports
...
```

## Why `.llm.md`?

When working with AI coding assistants, having a concise overview helps them understand your project structure quickly without needing to analyze every file. Think of it as a "map" for LLMs.

## License

MIT

