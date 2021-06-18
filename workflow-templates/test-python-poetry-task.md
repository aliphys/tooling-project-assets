# "Test Python" workflow (Poetry, Task)

Workflow file: [test-python-poetry-task.yml](test-python-poetry-task.yml)

Run [pytest](https://pytest.org)-based Python tests.

This is the version of the workflow for projects using the [Task](https://taskfile.dev/#/) task runner tool.

## Installation

The Python dependencies are managed by [Poetry](https://python-poetry.org/).

Install Poetry by following these instructions:<br />
https://python-poetry.org/docs/#installation

If your project does not already use Poetry, you can initialize the [`pyproject.toml`](https://python-poetry.org/docs/pyproject/) file using these commands:

```
poetry init --python="^3.9" --dev-dependency="pytest@^6.2.4"
poetry install
```

If already using Poetry, add the tool using this command:

```
poetry add --dev "pytest@^6.2.4"
```

Make sure to commit the resulting `pyproject.toml` and `poetry.lock` files.

## Assets

- [`Taskfile.yml`](assets/test-python-poetry-task/Taskfile.yml) - Test runner task.
  - Install to: repository root (or add the `python:test` task into the existing `Taskfile.yml`)
- [`Taskfile.yml`](assets/shared/Taskfile.yml) - Installation task.
  - Add the `poetry:install-deps` task into the existing `Taskfile.yml`
- [`__init__.py`](assets/test-python/__init__.py) - Python module file.
  - Install to: `/tests/`
- [`pytest.ini`](assets/test-python/pytest.ini) - [pytest](https://pytest.org) configuration file.
  - Install to: `/tests/`

## Readme badge

Markdown badge:

```markdown
[![Test Python status](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/test-python-poetry-task.yml/badge.svg)](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/test-python-poetry-task.yml)
```

Replace the `REPO_OWNER` and `REPO_NAME` placeholders in the URLs with the final repository owner and name ([example](https://raw.githubusercontent.com/arduino-libraries/ArduinoIoTCloud/master/README.md)).

---

Asciidoc badge:

```adoc
image:https://github.com/{repository-owner}/{repository-name}/actions/workflows/test-python-poetry-task.yml/badge.svg["Test Python status", link="https://github.com/{repository-owner}/{repository-name}/actions/workflows/test-python-poetry-task.yml"]
```

Define the `{repository-owner}` and `{repository-name}` attributes and use them throughout the readme ([example](https://raw.githubusercontent.com/arduino-libraries/WiFiNINA/master/README.adoc)).

## Commit message

```
Add CI workflow to run Python tests

On every push and pull request that affects relevant files, run the pytest-based Python tests.
```

## PR message

```markdown
On every push and pull request that affects relevant files, run the [pytest](https://pytest.org)-based Python tests.
```