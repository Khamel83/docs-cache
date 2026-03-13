# pytest Documentation

> Source: https://docs.pytest.org/
> Cached: 2026-02-13

## pytest: helps you write better programs

The `pytest` framework makes it easy to write small, readable tests, and can scale to support complex functional testing for applications and libraries.

**PyPI package name**: pytest

## A quick example

```python
# content of test_sample.py
def inc(x):
    return x + 1

def test_answer():
    assert inc(3) == 5
```

To execute it:

```bash
$ pytest
=========================== test session starts ============================
platform linux -- Python 3.x.y, pytest-9.x.y, pluggy-1.x.y
rootdir: /home/sweet/project
collected 1 item

test_sample.py F                                                     [100%]

================================= FAILURES =================================
_______________________________ test_answer ________________________________

    def test_answer():
>       assert inc(3) == 5
E       assert 4 == 5
E        +  where 4 = inc(3)

test_sample.py:6: AssertionError
========================= short test summary info ==========================
FAILED test_sample.py::test_answer - assert 4 == 5
============================ 1 failed in 0.12s =============================
```

Due to `pytest`'s detailed assertion introspection, only plain `assert` statements are used.

## Features

- Detailed info on failing assert statements (no need to remember `self.assert*` names)
- Auto-discovery of test modules and functions
- Modular fixtures for managing small or parametrized long-lived test resources
- Can run unittest (including trial) test suites out of the box
- Python 3.10+ or PyPy 3
- Rich plugin architecture, with over 1300+ external plugins and thriving community

## Documentation Sections

- **Get started** - install pytest and grasp its basics in just twenty minutes
- **How-to guides** - step-by-step guides, covering a vast range of use-cases and needs
- **Reference guides** - includes the complete pytest API reference, lists of plugins and more
- **Explanation** - background, discussion of key topics, answers to higher-level questions

## Bugs/Requests

Please use the GitHub issue tracker to submit bugs or request features.
