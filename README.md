# Stocks Analytics

- [Stocks Analytics](#Stocks Analytics)
- [Useful Commands](#useful-commands)
- [Goal](#goal)
  - [Overview](#overview)
  - [Reference](#reference)
- [Getting started](#getting-started)
  - [Install Pyenv](#install-pyenv)
  - [Make sure you have Python 3.9.](#make-sure-you-have-python-3.9.)
  - [Create a virtual environment](#create-a-virtual-environment)
  - [Activate the environment](#activate-the-environment)

Stocks Analytics project.
Data pipelines written in [Python 3](https://www.python.org/) on AWS stack and Snowflake.

# Useful Commands

| Command                   | Description                                                           |
|---------------------------|-----------------------------------------------------------------------|
| `./bin/reset-venv`        | Resets the virtual environement (useful if python version has changed)|
| `pytest`                  | Runs backend tests                                                    |                                     | Process background jobs                                                 |

# Goal

The goal is to build efficient analytical solution with scalable Data Warehouse on Snowflake.

## Overview

***Some overview***

## Reference

```commandline
http://docs.python.org/
```

# Getting started

Start by "cloning" this repository (repo) on to your laptop:

- Open a terminal and run `git clone {repo_url}` where `{repo_url}` is given by the **Clone or download** button above. You'll want to use **Clone with SSH** in that dialog, and you may have to [setup an SSH key first](https://help.github.com/en/articles/which-remote-url-should-i-use#cloning-with-ssh-urls).

### Install Pyenv

Update system packages.
```commandline
apt update -y
```

Install all of pyenv’s dependencies.
```commandline
apt install -y make build-essential libssl-dev zlib1g-dev \
> libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev\
> libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl\
> git
```

Clone the Repository.
```commandline
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

Configure the Environment.
```commandline
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n eval "$(pyenv init -)"\nfi' >> ~/.bashrc
```

Restart the shell.
```commandline
exec "$SHELL"
```

Verify the Installation.
```commandline
pyenv install --list
```

### Make sure you have Python 3.9.

Install python 3.9.6 with pyenv.

```bash
pyenv install 3.9.6
```

Set python 3.9.6 to be the globally available python version.

```bash
pyenv global 3.9.6
```

Double check your python installation:

```bash
❯ python --version
Python 3.9.6

❯ which python
/home/vshkuro/.pyenv/shims/python # note that we're referencing the pyenv installation instead of the default system one
```

At this point you should be good to proceed. Check out [this article to learn more about pyenv.](https://realpython.com/intro-to-pyenv/)

**Note**: if a different python installation is still being referenced at this point it may be addressed by the later step to activate the virtual environment. If you run into this you can continue to that step and try again.

### Create a virtual environment

Application depends on several Python modules, instead of installing them system-wide we create a [virtual environment](https://docs.python.org/3/tutorial/venv.html) in the repo folder:

```
./bin/setup-venv
```

### Activate the environment

```
. ./activate-venv
```

Now Python-related commands are running from this environment (you can just type `python` instead of `python3`). Installing packages with `pip` will install them for this environment only.

Deactivate the environment to go back to your normal system Python with `deactivate`.

You'll need to activate the environment every time you open a new terminal session. Most scripts in the `bin` folder will activate the environment for themselves automatically.
