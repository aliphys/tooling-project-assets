# "Check Markdown" workflow (Task)

Workflow file: [check-markdown-task.yml](check-markdown-task.yml)

Check the repository's Markdown files for problems:

- Use [markdownlint-cli](https://github.com/igorshubovych/markdownlint-cli) to check for common problems and formatting.
- Use [markdown-link-check](https://github.com/tcort/markdown-link-check) to check for broken links.

NOTE: This workflow is focused on linting. Formatting checks for Markdown are provided by the ["Check Prettier Formatting" workflow](check-prettier-formatting-task.md), so both should be used.

This is the version of the workflow for projects using the [Task](https://taskfile.dev/#/) task runner tool.

## Assets

- [`.markdown-link-check.json`](assets/check-markdown/.markdown-link-check.json) - markdown-link-check configuration file.
  - Install to: repository root
- [`.markdownlint.yml`](assets/check-markdown/.markdownlint.yml) - markdownlint configuration file.
  - Install to: repository root
- [`Taskfile.yml`](assets/check-markdown-task/Taskfile.yml] - Markdown tasks.
  - Install to: repository root (or add the `markdown:fix`, `markdown:lint`, and `markdown:check-links` tasks into the existing `Taskfile.yml`)

The code style defined in `.markdownlint.yml` is the official standardized style to be used in all Arduino tooling projects and should not be modified.

## Configuration

### markdownlint

In the event the repository contains externally maintained Markdown files, `markdownlint` can be configured to ignore them via a `.markdownlintignore` file:
https://github.com/igorshubovych/markdownlint-cli#ignoring-files

### markdown-link-check

Advanced configuration of `markdown-link-check` can be done via the [`.markdown-link-check.json`](assets/check-markdown/.markdown-link-check.json) configuration file:
https://github.com/gaurav-nelson/github-action-markdown-link-check#user-content-custom-variables:~:text=Specify%20a%20custom%20configuration%20file

## Readme badge

Markdown badge:

```markdown
[![Check Markdown status](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/check-markdown-task.yml/badge.svg)](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/check-markdown-task.yml)
```

Replace the `REPO_OWNER` and `REPO_NAME` placeholders in the URLs with the final repository owner and name ([example](https://raw.githubusercontent.com/arduino-libraries/ArduinoIoTCloud/master/README.md)).

---

Asciidoc badge:

```adoc
image:https://github.com/{repository-owner}/{repository-name}/actions/workflows/check-markdown-task.yml/badge.svg["Check Markdown status", link="https://github.com/{repository-owner}/{repository-name}/actions/workflows/check-markdown-task.yml"]
```

Define the `{repository-owner}` and `{repository-name}` attributes and use them throughout the readme ([example](https://raw.githubusercontent.com/arduino-libraries/WiFiNINA/master/README.adoc)).

## Commit message

```
Add CI workflow to check Markdown files for problems

On every push and pull request that affects relevant files, and periodically, check the repository's Markdown files for
problems:

- Use markdownlint to check for common problems and formatting.
- Use markdown-link-check to check for broken links.

The Arduino tooling Markdown style is defined by the `.markdownlint.yml` file.

In the event the repository contains externally maintained Markdown files, markdownlint can be configured to ignore them
via a `.markdownlintignore` file:
https://github.com/igorshubovych/markdownlint-cli#ignoring-files

markdown-link-check is configured via the `.markdown-link-check.json` file:
https://github.com/tcort/markdown-link-check#config-file-format
```

## PR message

```markdown
On every push and pull request that affects relevant files, and periodically, check the repository's Markdown files for
problems:

- Use [markdownlint-cli](https://github.com/igorshubovych/markdownlint-cli) to check for common problems and formatting.
- Use [markdown-link-check](https://github.com/tcort/markdown-link-check) to check for broken links.

The Arduino tooling Markdown style is defined by the `.markdownlint.yml` file.

In the event the repository contains externally maintained Markdown files, markdownlint can be configured to ignore them via a `.markdownlintignore` file:
https://github.com/igorshubovych/markdownlint-cli#ignoring-files

markdown-link-check is configured via the `.markdown-link-check.json` file:
https://github.com/tcort/markdown-link-check#config-file-format
```