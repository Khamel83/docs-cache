Title: Introduction | Documentation | Poetry

URL Source: https://python-poetry.org/docs

Markdown Content:
Introduction | Documentation | Poetry - Python dependency management and packaging made easy
===============

[Home![Image 1: Poetry logo](https://python-poetry.org/images/logo-origami.svg)](https://python-poetry.org/)

Search

 2.3 
*   [main](https://python-poetry.org/docs/main/)
*   [2.3](https://python-poetry.org/docs/)
*   [1.8](https://python-poetry.org/docs/1.8/)

Use dark mode

Open menu

*   [Documentation](https://python-poetry.org/docs/)[Introduction Poetry is a tool for dependency management and packaging in Python.](https://python-poetry.org/docs/)[Basic usage For the basic usage introduction we will be installing pendulum, a datetime library.](https://python-poetry.org/docs/basic-usage/)[Managing dependencies Poetry supports specifying main dependencies in the project.dependencies section of your pyproject.toml according to PEP 621.](https://python-poetry.org/docs/managing-dependencies/)[Libraries This chapter will tell you how to make your library installable through Poetry. Versioning Poetry requires PEP 440-compliant versions for all projects. While Poetry does not enforce any release convention, it used to encourage the use of semantic versioning within the scope of PEP 440 and supports version constraints that are especially suitable for semver. Note As an example, 1.0.0-hotfix.1 is not compatible with PEP 440.](https://python-poetry.org/docs/libraries/)[Commands You’ve already learned how to use the command-line interface to do some things.](https://python-poetry.org/docs/cli/)[Configuration Poetry can be configured via the config command (see more about its usage here) or directly in the config.toml file that will be automatically created when you first run that command.](https://python-poetry.org/docs/configuration/)[Repositories Poetry supports the use of PyPI and private repositories for discovery of packages as well as for publishing your projects. By default, Poetry is configured to use the PyPI repository, for package installation and publishing. So, when you add dependencies to your project, Poetry will assume they are available on PyPI. This represents most cases and will likely be enough for most users. Private Repository Example Installing from private package sources By default, Poetry discovers and installs packages from PyPI.](https://python-poetry.org/docs/repositories/)[Managing environments Poetry makes project environment isolation one of its core features. What this means is that it will always work isolated from your global Python installation.](https://python-poetry.org/docs/managing-environments/)[Dependency specification Dependencies for a project can be specified in various forms, which depend on the type of the dependency and on the optional constraints that might be needed for it to be installed. project.dependencies and tool.poetry.dependencies Prior Poetry 2.0, dependencies had to be declared in the tool.poetry.dependencies section of the pyproject.toml file. [tool.poetry.dependencies] requests = "^2.13.0" With Poetry 2.0, you should consider using the project.dependencies section instead. [project] # ...](https://python-poetry.org/docs/dependency-specification/)[Plugins Poetry supports using and building plugins if you wish to alter or expand Poetry’s functionality with your own. For example if your environment poses special requirements on the behaviour of Poetry which do not apply to the majority of its users or if you wish to accomplish something with Poetry in a way that is not desired by most users. In these cases you could consider creating a plugin to handle your specific logic. .](https://python-poetry.org/docs/plugins/)[The pyproject.toml file In package mode, the only required fields are name and version (either in the project section or in the tool.poetry section).](https://python-poetry.org/docs/pyproject/)[Contributing to Poetry First off, thanks for taking the time to contribute! The following is a set of guidelines for contributing to Poetry on GitHub.](https://python-poetry.org/docs/contributing/)[Community Badge For any projects using Poetry, you may add its official badge somewhere prominent like the README. Markdown [![Poetry](https://img.shields.io/endpoint?url=https://python-poetry.org/badge/v0.json)](https://python-poetry.org/) reStructuredText ..](https://python-poetry.org/docs/community/)[FAQ Why is the dependency resolution process slow? While the dependency resolver at the heart of Poetry is highly optimized and should be fast enough for most cases, with certain sets of dependencies, it can take time to find a valid solution. This is due to the fact that not all libraries on PyPI have properly declared their metadata and, as such, they are not available via the PyPI JSON API.](https://python-poetry.org/docs/faq/)[pre-commit hooks pre-commit is a framework for building and running git hooks.](https://python-poetry.org/docs/pre-commit-hooks/)[Building extension modules Building Extension Modules Warning While this feature has been around since almost the beginning of the Poetry project and has needed minimal changes, it is still considered unstable.](https://python-poetry.org/docs/building-extension-modules/) [2.3 Stable Documentation for the latest, **stable**, branch.](https://python-poetry.org/docs/)[main Development Documentation for the latest, **in-development**, branch.](https://python-poetry.org/docs/main/)    
*   [Blog](https://python-poetry.org/blog/)
*   [History](https://python-poetry.org/history/)
*   [](https://github.com/python-poetry/poetry "Go to the Github project")

![Image 2: Poetry logo](https://python-poetry.org/images/logo-origami.svg)

Close menu

[Documentation](https://python-poetry.org/docs/)[Blog](https://python-poetry.org/blog/)[History](https://python-poetry.org/history/)[](https://github.com/python-poetry/poetry "Go to the Github project")

*   [Introduction](https://python-poetry.org/docs/)
    *   [System requirements](https://python-poetry.org/docs#system-requirements)
    *   [Installation](https://python-poetry.org/docs#installation)
    *   [Enable tab completion for Bash, Fish, or Zsh](https://python-poetry.org/docs#enable-tab-completion-for-bash-fish-or-zsh)
        *   [Bash](https://python-poetry.org/docs#bash)
        *   [Fish](https://python-poetry.org/docs#fish)
        *   [Zsh](https://python-poetry.org/docs#zsh)

*   [Basic usage](https://python-poetry.org/docs/basic-usage/)
*   [Managing dependencies](https://python-poetry.org/docs/managing-dependencies/)
*   [Libraries](https://python-poetry.org/docs/libraries/)
*   [Commands](https://python-poetry.org/docs/cli/)
*   [Configuration](https://python-poetry.org/docs/configuration/)
*   [Repositories](https://python-poetry.org/docs/repositories/)
*   [Managing environments](https://python-poetry.org/docs/managing-environments/)
*   [Dependency specification](https://python-poetry.org/docs/dependency-specification/)
*   [Plugins](https://python-poetry.org/docs/plugins/)
*   [The pyproject.toml file](https://python-poetry.org/docs/pyproject/)
*   [Contributing to Poetry](https://python-poetry.org/docs/contributing/)
*   [Community](https://python-poetry.org/docs/community/)
*   [FAQ](https://python-poetry.org/docs/faq/)
*   [pre-commit hooks](https://python-poetry.org/docs/pre-commit-hooks/)
*   [Building extension modules](https://python-poetry.org/docs/building-extension-modules/)

 Introduction
*   [Introduction](https://python-poetry.org/docs/)
*   [Basic usage](https://python-poetry.org/docs/basic-usage/)
*   [Managing dependencies](https://python-poetry.org/docs/managing-dependencies/)
*   [Libraries](https://python-poetry.org/docs/libraries/)
*   [Commands](https://python-poetry.org/docs/cli/)
*   [Configuration](https://python-poetry.org/docs/configuration/)
*   [Repositories](https://python-poetry.org/docs/repositories/)
*   [Managing environments](https://python-poetry.org/docs/managing-environments/)
*   [Dependency specification](https://python-poetry.org/docs/dependency-specification/)
*   [Plugins](https://python-poetry.org/docs/plugins/)
*   [The pyproject.toml file](https://python-poetry.org/docs/pyproject/)
*   [Contributing to Poetry](https://python-poetry.org/docs/contributing/)
*   [Community](https://python-poetry.org/docs/community/)
*   [FAQ](https://python-poetry.org/docs/faq/)
*   [pre-commit hooks](https://python-poetry.org/docs/pre-commit-hooks/)
*   [Building extension modules](https://python-poetry.org/docs/building-extension-modules/)

Introduction
============

*   [System requirements](https://python-poetry.org/docs#system-requirements)
*   [Installation](https://python-poetry.org/docs#installation)
*   [Enable tab completion for Bash, Fish, or Zsh](https://python-poetry.org/docs#enable-tab-completion-for-bash-fish-or-zsh)
    *   [Bash](https://python-poetry.org/docs#bash)
    *   [Fish](https://python-poetry.org/docs#fish)
    *   [Zsh](https://python-poetry.org/docs#zsh)

Introduction [#](https://python-poetry.org/docs#introduction)
=============================================================

Poetry is a tool for **dependency management** and **packaging** in Python. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you. Poetry offers a lockfile to ensure repeatable installs, and can build your project for distribution.

System requirements [#](https://python-poetry.org/docs#system-requirements)
---------------------------------------------------------------------------

Poetry requires **Python 3.9+**. It is multi-platform and the goal is to make it work equally well on Linux, macOS and Windows.

Installation [#](https://python-poetry.org/docs#installation)
-------------------------------------------------------------

Note

If you are viewing documentation for the development branch, you may wish to install a preview or development version of Poetry. See the **advanced** installation instructions to use a preview or alternate version of Poetry.

 With pipx 
*   [With pipx](https://python-poetry.org/docs#installing-with-pipx)
*   [With the official installer](https://python-poetry.org/docs#installing-with-the-official-installer)
*   [Manually (advanced)](https://python-poetry.org/docs#installing-manually)
*   [CI recommendations](https://python-poetry.org/docs#ci-recommendations)

[With pipx](https://python-poetry.org/docs#installing-with-pipx)[With the official installer](https://python-poetry.org/docs#installing-with-the-official-installer)[Manually (advanced)](https://python-poetry.org/docs#installing-manually)[CI recommendations](https://python-poetry.org/docs#ci-recommendations)

[`pipx`](https://github.com/pypa/pipx) is used to install Python CLI applications globally while still isolating them in virtual environments. `pipx` will manage upgrades and uninstalls when used to install Poetry.

1.   **Install pipx**

If `pipx` is not already installed, you can follow any of the options in the [official pipx installation instructions](https://pipx.pypa.io/stable/installation/). Any non-ancient version of `pipx` will do.

2.   **Install Poetry**

![Image 3: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
pipx install poetry
``` 
3.   **Install Poetry (advanced)**

Note You can skip this step, if you simply want the latest version and already installed Poetry as described in the previous step. This step details advanced usages of this installation method. For example, installing Poetry from source, having multiple versions installed at the same time etc.  
`pipx` can install different versions of Poetry, using the same syntax as pip:

![Image 4: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
pipx install poetry==1.8.4
``` 
`pipx` can also install versions of Poetry in parallel, which allows for easy testing of alternate or prerelease versions. Each version is given a unique, user-specified suffix, which will be used to create a unique binary name:

![Image 5: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
pipx install --suffix=@1.8.4 poetry==1.8.4
poetry@1.8.4 --version
``` ![Image 6: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
pipx install --suffix=@preview --pip-args=--pre poetry
poetry@preview --version
``` 
Finally, `pipx` can install any valid [pip requirement spec](https://pip.pypa.io/en/stable/cli/pip_install/), which allows for installations of the development version from `git`, or even for local testing of pull requests:

![Image 7: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
pipx install --suffix @main git+https://github.com/python-poetry/poetry.git@main
pipx install --suffix @pr1234 git+https://github.com/python-poetry/poetry.git@refs/pull/1234/head
``` 
4.   **Update Poetry**

![Image 8: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
pipx upgrade poetry
``` 
5.   **Uninstall Poetry**

![Image 9: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
pipx uninstall poetry
``` 

We provide a custom installer that will install Poetry in a new virtual environment and allows Poetry to manage its own environment.

1.   **Install Poetry**

The installer script is available directly at [install.python-poetry.org](https://install.python-poetry.org/), and is developed in [its own repository](https://github.com/python-poetry/install.python-poetry.org). The script can be executed directly (i.e. ‘curl python’) or downloaded and then executed from disk (e.g. in a CI environment).

**Linux, macOS, Windows (WSL)**

![Image 10: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
curl -sSL https://install.python-poetry.org | python3 -
``` 
**Windows (Powershell)**

![Image 11: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```powershell
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -
``` Note If you have installed Python through the Microsoft Store, replace `py` with `python` in the command above.  
2.   **Install Poetry (advanced)**

Note You can skip this step, if you simply want the latest version and already installed Poetry as described in the previous step. This step details advanced usages of this installation method. For example, installing Poetry from source, using a pre-release build, configuring a different installation location etc.  
By default, Poetry is installed into a platform and user-specific directory:

    *   `~/Library/Application Support/pypoetry` on macOS.
    *   `~/.local/share/pypoetry` on Linux/Unix.
    *   `%APPDATA%\pypoetry` on Windows.

If you wish to change this, you may define the `$POETRY_HOME` environment variable:

![Image 12: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
curl -sSL https://install.python-poetry.org | POETRY_HOME=/etc/poetry python3 -
```

If you want to install prerelease versions, you can do so by passing the `--preview` option to the installation script or by using the `$POETRY_PREVIEW` environment variable:

![Image 13: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
curl -sSL https://install.python-poetry.org | python3 - --preview
curl -sSL https://install.python-poetry.org | POETRY_PREVIEW=1 python3 -
```

Similarly, if you want to install a specific version, you can use `--version` option or the `$POETRY_VERSION` environment variable:

![Image 14: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
curl -sSL https://install.python-poetry.org | python3 - --version 1.8.4
curl -sSL https://install.python-poetry.org | POETRY_VERSION=1.8.4 python3 -
```

You can also install Poetry from a `git` repository by using the `--git` option:

![Image 15: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
curl -sSL https://install.python-poetry.org | python3 - --git https://github.com/python-poetry/poetry.git@main
```

If you want to install different versions of Poetry in parallel, a good approach is the installation with pipx and suffix.

3.   **Add Poetry to your PATH**

The installer creates a `poetry` wrapper in a well-known, platform-specific directory:

    *   `$HOME/.local/bin` on Unix.
    *   `%APPDATA%\Python\Scripts` on Windows.
    *   `$POETRY_HOME/bin` if `$POETRY_HOME` is set.

If this directory is not present in your `$PATH`, you can add it in order to invoke Poetry as `poetry`.

Alternatively, the full path to the `poetry` binary can always be used:

    *   `~/Library/Application Support/pypoetry/venv/bin/poetry` on macOS.
    *   `~/.local/share/pypoetry/venv/bin/poetry` on Linux/Unix.
    *   `%APPDATA%\pypoetry\venv\Scripts\poetry` on Windows.
    *   `$POETRY_HOME/venv/bin/poetry` if `$POETRY_HOME` is set.

4.   **Use Poetry**

Once Poetry is installed and in your `$PATH`, you can execute the following:

![Image 16: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
poetry --version
``` 
If you see something like `Poetry (version 2.0.0)`, your installation is ready to use!

5.   **Update Poetry**

Poetry is able to update itself when installed using the official installer.

Warning Especially on Windows, `self update` may be problematic so that a re-install with the installer should be preferred.  ![Image 17: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
poetry self update
``` 
If you want to install pre-release versions, you can use the `--preview` option.

![Image 18: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
poetry self update --preview
``` 
And finally, if you want to install a specific version, you can pass it as an argument to `self update`.

![Image 19: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
poetry self update 1.8.4
``` 
6.   **Uninstall Poetry**

If you decide Poetry isn’t your thing, you can completely remove it from your system by running the installer again with the `--uninstall` option or by setting the `POETRY_UNINSTALL` environment variable before executing the installer.

![Image 20: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
curl -sSL https://install.python-poetry.org | python3 - --uninstall
curl -sSL https://install.python-poetry.org | POETRY_UNINSTALL=1 python3 -
``` 

Poetry can be installed manually using `pip` and the `venv` module. By doing so you will essentially perform the steps carried out by the official installer. As this is an advanced installation method, these instructions are Unix-only and omit specific examples such as installing from `git`.

The variable `$VENV_PATH` will be used to indicate the path at which the virtual environment was created.

![Image 21: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
python3 -m venv $VENV_PATH
$VENV_PATH/bin/pip install -U pip setuptools
$VENV_PATH/bin/pip install poetry
```

Poetry will be available at `$VENV_PATH/bin/poetry` and can be invoked directly or symlinked elsewhere.

To uninstall Poetry, simply delete the entire `$VENV_PATH` directory.

Unlike development environments, where making use of the latest tools is desirable, in a CI environment reproducibility should be made the priority. Here are some suggestions for installing Poetry in such an environment.

**Version pinning**

Whatever method you use, it is highly recommended to explicitly control the version of Poetry used, so that you are able to upgrade after performing your own validation. Each install method has a different syntax for setting the version that is used in the following examples.

**Using pipx**

Just as `pipx` is a powerful tool for development use, it is equally useful in a CI environment and should be one of your top choices for use of Poetry in CI.

![Image 22: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
pipx install poetry==2.0.0
```

**Using install.python-poetry.org**

Note

The official installer script ([install.python-poetry.org](https://install.python-poetry.org/)) offers a streamlined and simplified installation of Poetry, sufficient for developer use or for simple pipelines. However, in a CI environment the other two supported installation methods (pipx and manual) should be seriously considered.

Downloading a copy of the installer script to a place accessible by your CI pipelines (or maintaining a copy of the [repository](https://github.com/python-poetry/install.python-poetry.org)) is strongly suggested, to ensure your pipeline’s stability and to maintain control over what code is executed.

By default, the installer will install to a user-specific directory. In more complex pipelines that may make accessing Poetry difficult (especially in cases like multi-stage container builds). It is highly suggested to make use of `$POETRY_HOME` when using the official installer in CI, as that way the exact paths can be controlled.

![Image 23: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
export POETRY_HOME=/opt/poetry
python3 install-poetry.py --version 2.0.0
$POETRY_HOME/bin/poetry --version
```

**Using pip (aka manually)**

For maximum control in your CI environment, installation with `pip` is fully supported and something you should consider. While this requires more explicit commands and knowledge of Python packaging from you, it in return offers the best debugging experience, and leaves you subject to the fewest external tools.

![Image 24: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
export POETRY_HOME=/opt/poetry
python3 -m venv $POETRY_HOME
$POETRY_HOME/bin/pip install poetry==2.0.0
$POETRY_HOME/bin/poetry --version
```

Note

If you install Poetry via `pip`, ensure you have Poetry installed into an isolated environment that is **not the same** as the target environment managed by Poetry. If Poetry and your project are installed into the same environment, Poetry is likely to upgrade or uninstall its own dependencies (causing hard-to-debug and understand errors).

Warning

Poetry should always be installed in a dedicated virtual environment to isolate it from the rest of your system. Each of the above described installation methods ensures that. It should in no case be installed in the environment of the project that is to be managed by Poetry. This ensures that Poetry’s own dependencies will not be accidentally upgraded or uninstalled. In addition, the isolated virtual environment in which poetry is installed should not be activated for running poetry commands.

Enable tab completion for Bash, Fish, or Zsh [#](https://python-poetry.org/docs#enable-tab-completion-for-bash-fish-or-zsh)
---------------------------------------------------------------------------------------------------------------------------

`poetry` supports generating completion scripts for Bash, Fish, and Zsh.

Note

You may need to restart your shell in order for these changes to take effect.

See `poetry help completions` for full details, but the gist is as simple as using one of the following:

### Bash [#](https://python-poetry.org/docs#bash)

#### Auto-loaded (recommended) [#](https://python-poetry.org/docs#auto-loaded-recommended)

![Image 25: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
poetry completions bash >> ~/.bash_completion
```

#### Lazy-loaded [#](https://python-poetry.org/docs#lazy-loaded)

![Image 26: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
poetry completions bash > ${XDG_DATA_HOME:-~/.local/share}/bash-completion/completions/poetry
```

### Fish [#](https://python-poetry.org/docs#fish)

![Image 27: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```fish
poetry completions fish > ~/.config/fish/completions/poetry.fish
```

### Zsh [#](https://python-poetry.org/docs#zsh)

![Image 28: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```zsh
poetry completions zsh > ~/.zfunc/_poetry
```

You must then add the following lines in your `~/.zshrc`, if they do not already exist:

![Image 29: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```bash
fpath+=~/.zfunc
autoload -Uz compinit && compinit
```

#### Oh My Zsh [#](https://python-poetry.org/docs#oh-my-zsh)

![Image 30: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```zsh
mkdir $ZSH_CUSTOM/plugins/poetry
poetry completions zsh > $ZSH_CUSTOM/plugins/poetry/_poetry
```

You must then add `poetry` to your plugins array in `~/.zshrc`:

![Image 31: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```text
plugins(
	poetry
	...
	)
```

#### Prezto [#](https://python-poetry.org/docs#prezto)

![Image 32: A 16x16 small image, likely a logo, icon or avatar](blob:http://localhost/18207ed4dfd0c426d14a577bfe3b599e)
```zsh
poetry completions zsh > ~/.zprezto/modules/completion/external/src/_poetry
```

If completions still don’t work, try removing `~/.cache/prezto/zcompcache` and starting a new shell.

Footer
------

![Image 33: Poetry logo](https://python-poetry.org/images/logo-origami.svg)
Python packaging and dependency management made easy.

[GitHub](https://github.com/python-poetry)[Discord](https://discord.com/invite/awxPgve)

### Documentation

*   [Introduction](https://python-poetry.org/docs/)
*   [Basic usage](https://python-poetry.org/docs/basic-usage/)
*   [Managing dependencies](https://python-poetry.org/docs/managing-dependencies/)
*   [Libraries](https://python-poetry.org/docs/libraries/)
*   [Commands](https://python-poetry.org/docs/cli/)
*   [Configuration](https://python-poetry.org/docs/configuration/)
*   [Repositories](https://python-poetry.org/docs/repositories/)
*   [Managing environments](https://python-poetry.org/docs/managing-environments/)
*   [Dependency specification](https://python-poetry.org/docs/dependency-specification/)
*   [Plugins](https://python-poetry.org/docs/plugins/)
*   [The pyproject.toml file](https://python-poetry.org/docs/pyproject/)
*   [Contributing to Poetry](https://python-poetry.org/docs/contributing/)
*   [Community](https://python-poetry.org/docs/community/)
*   [FAQ](https://python-poetry.org/docs/faq/)
*   [pre-commit hooks](https://python-poetry.org/docs/pre-commit-hooks/)
*   [Building extension modules](https://python-poetry.org/docs/building-extension-modules/)

### Github

*   [Project](https://github.com/python-poetry/poetry)
*   [Issues](https://github.com/python-poetry/poetry/issues)
*   [Discussions](https://github.com/python-poetry/poetry/discussions)

### Other Projects

*   [poetry-core](https://github.com/python-poetry/poetry-core)
*   [install.python-poetry.org](https://github.com/python-poetry/install.python-poetry.org)
*   [Bundle plugin](https://github.com/python-poetry/poetry-plugin-bundle)
*   [Export plugin](https://github.com/python-poetry/poetry-plugin-export)

Copyright © 2018-2026. All Rights Reserved. Powered by [](https://vercel.com/?utm_source=python-poetry&utm_campaign=oss "Go to the Vercel website")
