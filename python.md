# OKTET Python development guide

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [OKTET Python development guide](#oktet-python-development-guide)
    - [Versions and dependencies](#versions-and-dependencies)
    - [Config file](#config-file)
    - [Ruff: code format](#ruff-code-format)
    - [Ruff: linters](#ruff-linters)
    - [mypy: type checking](#mypy-type-checking)
    - [Project scripting](#project-scripting)

<!-- markdown-toc end -->

## Versions and dependencies

Python version depends on the system you're targeting. Keep in mind that:

- you MUST NOT write new code for `python2.x`;
- you MUST NOT rely on packages that can't be installed via `pip` OR your distro
  (`apt/dnf/yum`) OR bundled with your scripts;
- you SHOULD use `python -m pip install` instead of simply `pip install`,
  where `python` is certain Python interpreter version you intend to use.

## Config file

Use `pyproject.toml` from `python/` directory of this styleguide and put it into the root of your project.

Don't use or have any other files in your project unless absolutely necessary.

## Ruff: code format

Use `ruff format`.

See https://github.com/astral-sh/ruff?tab=readme-ov-file#usage

## Ruff: linters

Use `ruff check`.

See https://github.com/astral-sh/ruff?tab=readme-ov-file#usage

## mypy: type checking

If writing on python3 you MUST use type annotation and you MUST have a clean
mypy run with the config from `python/`

`mypy` version to be used: at least 0.8. Can be installed from `pip` or
automatically by the IDE.

## Project scripting

Project should have 3 scripts:

 - `pyformat` should apply all agreed formatters,
 - `pycheck` should apply all agreed linters,
 - `pytest` should run all the selftest tests that you have if any.
