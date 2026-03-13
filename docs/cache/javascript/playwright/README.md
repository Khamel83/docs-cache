# Playwright Python Documentation

> Source: https://playwright.dev/python/docs/intro
> Cached: 2026-02-13

## Introduction

Playwright was created specifically to accommodate the needs of end-to-end testing. Playwright supports all modern rendering engines including Chromium, WebKit, and Firefox. Test on Windows, Linux, and macOS, locally or on CI, headless or headed with native mobile emulation.

The Playwright library can be used as a general purpose browser automation tool, providing a powerful set of APIs to automate web applications, for both sync and async Python.

## Installing Playwright Pytest

```bash
pip install pytest-playwright
playwright install
```

## Example Test

```python
import re
from playwright.sync_api import Page, expect

def test_has_title(page: Page):
    page.goto("https://playwright.dev/")
    # Expect a title "to contain" a substring.
    expect(page).to_have_title(re.compile("Playwright"))

def test_get_started_link(page: Page):
    page.goto("https://playwright.dev/")
    # Click the get started link.
    page.get_by_role("link", name="Get started").click()
    # Expects page to have a heading with the name of Installation.
    expect(page.get_by_role("heading", name="Installation")).to_be_visible()
```

## Running Tests

```bash
pytest
```

By default tests will be run on chromium. This can be configured via the CLI options. Tests are run in headless mode meaning no browser UI will open up when running the tests.

## System Requirements

- Python 3.8 or higher.
- Windows 11+, Windows Server 2019+ or Windows Subsystem for Linux (WSL).
- macOS 14 Ventura, or later.
- Debian 12, Debian 13, Ubuntu 22.04, Ubuntu 24.04, on x86-64 and arm64 architecture.

## Features

- Supports Chromium, WebKit, and Firefox
- Cross-platform testing (Windows, Linux, macOS)
- Headless and headed modes
- Native mobile emulation
- Context isolation
- Multiple browser configurations out of the box
