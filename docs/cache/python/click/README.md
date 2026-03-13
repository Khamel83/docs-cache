# Click Documentation

> Python package for creating beautiful command line interfaces in a composable way.

**URL**: https://click.palletsprojects.com/
**Cached**: 2026-02-08
**Version**: 8.1.x

## Overview

Click is the "Command Line Interface Creation Kit" for Python. It aims to make writing command line tools quick and fun while preventing frustration.

### Key Features

- Arbitrary nesting of commands
- Automatic help page generation
- Supports lazy loading of subcommands at runtime
- Highly configurable with sensible defaults

### Example

```python
import click

@click.command()
@click.option('--count', default=1, help='Number of greetings.')
@click.option('--name', prompt='Your name',
              help='The person to greet.')
def hello(count, name):
    """Simple program that greets NAME for a total of COUNT times."""
    for x in range(count):
        click.echo(f"Hello {name}!")

if __name__ == '__main__':
    hello()
```

## Documentation Structure

### User Guide
- **Why Click?** - Philosophy and comparisons to argparse, docopt
- **Quickstart** - Basic concepts, creating commands, echoing, nesting
- **Setuptools Integration** - Script packaging
- **Parameters** - Types, names, custom types
- **Options** - Name options, multi-value, boolean flags, prompts, environment variables
- **Arguments** - Basic, variadic, file arguments
- **Commands and Groups** - Nested handling, contexts, multi-commands
- **User Input Prompts** - Option prompts, input prompts, confirmation
- **Documenting Scripts** - Help texts, meta variables
- **Complex Applications** - Building a git clone, lazy loading
- **Advanced Patterns** - Aliases, token normalization, invoking commands
- **Testing** - Basic testing, file system isolation
- **Utilities** - Printing, ANSI colors, progress bars, editors
- **Shell Completion** - Enabling and customizing completion
- **Exception Handling** - Error handling strategies
- **Unicode Support** - Surrogate handling

### API Reference
- Decorators
- Utilities
- Commands
- Parameters
- Context
- Types
- Exceptions
- Formatting
- Parsing

## Common Patterns

### Command Groups
```python
@click.group()
def cli():
    pass

@cli.command()
def init():
    click.echo('Initialized')

@cli.command()
def status():
    click.echo('Status: OK')
```

### Environment Variables
```python
@click.option('--username', envvar='USER')
def hello(username):
    click.echo(f"Hello {username}")
```

### File Arguments
```python
@click.argument('input', type=click.File('r'))
@click.argument('output', type=click.File('w'))
def process(input, output):
    for line in input:
        output.write(line.upper())
```

### Progress Bars
```python
with click.progressbar(items, label='Processing') as bar:
    for item in bar:
        process_item(item)
```

## Key Decorators

- `@click.command()` - Create a command
- `@click.group()` - Create a command group
- `@click.option()` - Add an option
- `@click.argument()` - Add an argument
- `@click.pass_context` - Pass context object
- `@click.pass_obj` - Pass object through context

## Parameter Types

- `str` - Text
- `int` / `float` - Numbers
- `bool` - Boolean (for flags)
- `click.File(mode)` - File objects
- `click.Path` - File system paths
- `click.Choice(['a', 'b'])` - Limited choices
- `click.DateTime` - Date/time parsing

## Testing Click Apps

```python
from click.testing import CliRunner

def test_hello():
    runner = CliRunner()
    result = runner.invoke(hello, ['--name', 'World'])
    assert result.exit_code == 0
    assert 'Hello World' in result.output
```

## Shell Completion

Click supports automatic shell completion for Bash, Zsh, and Fish.

```python
# Enable completion
@click.command()
@click.argument('name', autocompletion=function_that_completes)
def mycommand(name):
    pass
```

## External Links

- GitHub: https://github.com/pallets/click
- PyPI: https://pypi.org/project/click/
- Changelog: https://click.palletsprojects.com/en/latest/changes/
