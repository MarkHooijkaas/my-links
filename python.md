
# python tools
- https://www.playfulpython.com/environment-tools-pdm-poetry-rye/
- https://peps.python.org/pep-0582/  use of local packages
- https://stackoverflow.com/questions/22241420/execution-of-python-code-with-m-option-or-not
- https://chriswarrick.com/blog/2023/01/15/how-to-improve-python-packaging/ How to improve Python packaging, or why fourteen tools are at least twelve too many
- https://www.laac.dev/blog/setting-up-modern-python-development-environment-ubuntu-20/
- https://jacobian.org/2019/nov/11/python-environment-2020/
- https://pypa.github.io/pipx/how-pipx-works/

# packaging
- https://stackoverflow.com/questions/54597212/using-hyphen-dash-in-python-repository-name-and-package-name/54599368#54599368
- https://labdmitriy.github.io/blog/distributions-vs-packages/#additional-experiments
- https://pythonpackaging.info/07-Package-Release.html
- https://carpentries-incubator.github.io/python_packaging/04-history-of-packaging.html

# venv
- https://stackoverflow.com/questions/41573587/what-is-the-difference-between-venv-pyvenv-pyenv-virtualenv-virtualenvwrappe
- https://virtualenv.pypa.io/en/latest/  # features in virtualenv, not in venv
- https://pythonhow.com/what/what-is-the-difference-between-venv-pyvenv-pyenv-virtualenv-virtualenvwrapper-pipenv/
- https://peps.python.org/pep-0405/

# pipenv
- https://chriswarrick.com/blog/2018/07/17/pipenv-promises-a-lot-delivers-very-little/
- https://docs.python-guide.org/dev/virtualenvs/
- https://pypi.org/project/onepm/
- https://pypi.org/project/pipenv/
- https://pipenv.pypa.io/en/latest/
- https://github.com/pypa/pipenv


# misc
- https://github.com/pallets/jinja/tree/3.1.2  jinja source code
- https://github.com/crdoconnor/strictyaml/tree/master
- https://hitchdev.com/strictyaml/features-removed/
- https://hitchdev.com/strictyaml/why/flow-style-removed/
- https://hitchdev.com/strictyaml/why/implicit-typing-removed/ The Norway problem
- https://pep8.org/#indentation PEP8

## https://stackoverflow.com/questions/41573587/what-is-the-difference-between-venv-pyvenv-pyenv-virtualenv-virtualenvwrappe
PyPI packages not in the standard library:
-    virtualenv is a very popular tool that creates isolated Python environments for Python libraries. If you're not familiar with this tool, I highly recommend learning it, as it is a very useful tool.
-    It works by installing a bunch of files in a directory (eg: env/), and then modifying the PATH environment variable to prefix it with a custom bin directory (eg: env/bin/). An exact copy of the python or python3 binary is placed in this directory, but Python is programmed to look for libraries relative to its path first, in the environment directory. It's not part of Python's standard library, but is officially blessed by the PyPA (Python Packaging Authority). Once activated, you can install packages in the virtual environment using pip.
-    pyenv is used to isolate Python versions. For example, you may want to test your code against Python 2.7, 3.6, 3.7 and 3.8, so you'll need a way to switch between them. Once activated, it prefixes the PATH environment variable with ~/.pyenv/shims, where there are special files matching the Python commands (python, pip). These are not copies of the Python-shipped commands; they are special scripts that decide on the fly which version of Python to run based on the PYENV_VERSION environment variable, or the .python-version file, or the ~/.pyenv/version file. pyenv also makes the process of downloading and installing multiple Python versions easier, using the command pyenv install.
-    pyenv-virtualenv is a plugin for pyenv by the same author as pyenv, to allow you to use pyenv and virtualenv at the same time conveniently. However, if you're using Python 3.3 or later, pyenv-virtualenv will try to run python -m venv if it is available, instead of virtualenv. You can use virtualenv and pyenv together without pyenv-virtualenv, if you don't want the convenience features.
-    virtualenvwrapper is a set of extensions to virtualenv (see docs). It gives you commands like mkvirtualenv, lssitepackages, and especially workon for switching between different virtualenv directories. This tool is especially useful if you want multiple virtualenv directories.
-    pyenv-virtualenvwrapper is a plugin for pyenv by the same author as pyenv, to conveniently integrate virtualenvwrapper into pyenv.
-    pipenv aims to combine Pipfile, pip and virtualenv into one command on the command-line. The virtualenv directory typically gets placed in ~/.local/share/virtualenvs/XXX, with XXX being a hash of the path of the project directory. This is different from virtualenv, where the directory is typically in the current working directory. pipenv is meant to be used when developing Python applications (as opposed to libraries). There are alternatives to pipenv, such as poetry, which I won't list here since this question is only about the packages that are similarly named.


## https://pythonhow.com/what/what-is-the-difference-between-venv-pyvenv-pyenv-virtualenv-virtualenvwrapper-pipenv/
All of these tools are used to create isolated Python environments, but they differ in terms of their purpose, functionality, and the level of complexity they provide. Here there's a wider explanation:

1. venv: This is a built-in module in Python 3.3 and later versions that allows you to create virtual environments in Python. It creates a new Python environment with its own site directories, which can be used to install and manage packages for specific projects. It's simple, lightweight, and easy to use.
2. pyvenv: This is a deprecated tool in Python 3.6 and later versions that is similar to venv. It's no longer recommended to use this tool as it has been replaced by the venv module.
3. pyenv: This is a tool that allows you to manage multiple versions of Python on your machine. It's not specifically designed for creating virtual environments, but it allows you to switch between different versions of Python on the fly.
4. virtualenv: This is a popular third-party tool that allows you to create isolated Python environments. It works with both Python 2 and 3 and allows you to create virtual environments with different Python versions, which can be useful for testing your code across different Python versions.
5. virtualenvwrapper: This is a set of extensions to virtualenv that makes it easier to manage virtual environments. It provides commands to create, activate, and delete virtual environments, and allows you to organize your environments in a more structured way.
6. pipenv: This is a tool that combines virtual environments with package management. It creates a new virtual environment for each project and automatically installs the required packages from a Pipfile. It's designed to simplify the process of managing dependencies for your projects and provides a simpler interface than virtualenv.

In summary, venv and virtualenv are similar in functionality but differ in implementation, where venv is a built-in module in Python 3 while virtualenv is a third-party tool. pyvenv is a deprecated tool that has been replaced by venv. pyenv is a tool that allows you to manage multiple Python versions on your machine. virtualenvwrapper is an extension to virtualenv that provides additional functionality for managing virtual environments. pipenv combines virtual environments with package management.
