https://github.com/astral-sh/uv  
https://qiita.com/gomi1994/items/ce92af2386cdd94c6fc3  
各コマンドは、「Cache options」「Global options」は共通
## Usage
```
Usage: uv [OPTIONS] <COMMAND>

Commands:
  run                        Run a command or script
  init                       Create a new project
  add                        Add dependencies to the project
  remove                     Remove dependencies from the project
  sync                       Update the project's environment
  lock                       Update the project's lockfile
  export                     Export the project's lockfile to an alternate format
  tree                       Display the project's dependency tree
  tool                       Run and install commands provided by Python packages
  python                     Manage Python versions and installations
  pip                        Manage Python packages with a pip-compatible interface
  venv                       Create a virtual environment
  build                      Build Python packages into source distributions and wheels
  publish                    Upload distributions to an index
  cache                      Manage uv's cache
  self                       Manage the uv executable
  version                    Display uv's version
  generate-shell-completion  Generate shell completion
  help                       Display documentation for a command

Cache options:
  -n, --no-cache               Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation [env: UV_NO_CACHE=]
      --cache-dir <CACHE_DIR>  Path to the cache directory [env: UV_CACHE_DIR=]

Python options:
      --managed-python       Require use of uv-managed Python versions [env: UV_MANAGED_PYTHON=]
      --no-managed-python    Disable use of uv-managed Python versions [env: UV_NO_MANAGED_PYTHON=]
      --no-python-downloads  Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]

Global options:
  -q, --quiet...                                   Use quiet output
  -v, --verbose...                                 Use verbose output
      --color <COLOR_CHOICE>                       Control the use of color in output [possible values: auto, always, never]
      --native-tls                                 Whether to load TLS certificates from the platform's native certificate store [env: UV_NATIVE_TLS=]
      --offline                                    Disable network access [env: UV_OFFLINE=]
      --allow-insecure-host <ALLOW_INSECURE_HOST>  Allow insecure connections to a host [env: UV_INSECURE_HOST=]
      --no-progress                                Hide all progress outputs [env: UV_NO_PROGRESS=]
      --directory <DIRECTORY>                      Change to the given directory prior to running the command
      --project <PROJECT>                          Run the command within the given project directory [env: UV_PROJECT=]
      --config-file <CONFIG_FILE>                  The path to a `uv.toml` file to use for configuration [env: UV_CONFIG_FILE=]
      --no-config                                  Avoid discovering configuration files (`pyproject.toml`, `uv.toml`) [env: UV_NO_CONFIG=]
  -h, --help                                       Display the concise help for this command
  -V, --version                                    Display the uv version

Use `uv help <command>` for more information on a specific command.
```


## init
```
Create a new project

Usage: uv init [OPTIONS] [PATH]

Arguments:
  [PATH]  The path to use for the project/script

Options:
      --name <NAME>                    The name of the project
      --bare                           Only create a `pyproject.toml`
      --package                        Set up the project to be built as a Python package
      --no-package                     Do not set up the project to be built as a Python package
      --app                            Create a project for an application
      --lib                            Create a project for a library
      --script                         Create a script
      --description <DESCRIPTION>      Set the project description
      --no-description                 Disable the description for the project
      --vcs <VCS>                      Initialize a version control system for the project [possible values: git, none]
      --build-backend <BUILD_BACKEND>  Initialize a build-backend of choice for the project [possible values: hatch, flit, pdm, setuptools, maturin, scikit]
      --no-readme                      Do not create a `README.md` file
      --author-from <AUTHOR_FROM>      Fill in the `authors` field in the `pyproject.toml` [possible values: auto, git, none]
      --no-pin-python                  Do not create a `.python-version` file for the project
      --no-workspace                   Avoid discovering a workspace and create a standalone project

Python options:
  -p, --python <PYTHON>      The Python interpreter to use to determine the minimum supported Python version. [env: UV_PYTHON=]
      --managed-python       Require use of uv-managed Python versions [env: UV_MANAGED_PYTHON=]
      --no-managed-python    Disable use of uv-managed Python versions [env: UV_NO_MANAGED_PYTHON=]
      --no-python-downloads  Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]
```


## sync
```
Update the project's environment

Usage: uv sync [OPTIONS]

Options:
      --extra <EXTRA>                            Include optional dependencies from the specified extra name
      --all-extras                               Include all optional dependencies
      --no-extra <NO_EXTRA>                      Exclude the specified optional dependencies, if `--all-extras` is supplied
      --no-dev                                   Disable the development dependency group
      --only-dev                                 Only include the development dependency group
      --group <GROUP>                            Include dependencies from the specified dependency group
      --no-group <NO_GROUP>                      Disable the specified dependency group
      --no-default-groups                        Ignore the default dependency groups
      --only-group <ONLY_GROUP>                  Only include dependencies from the specified dependency group
      --all-groups                               Include dependencies from all dependency groups
      --no-editable                              Install any editable dependencies, including the project and any workspace members, as non-editable
      --inexact                                  Do not remove extraneous packages present in the environment
      --active                                   Sync dependencies to the active virtual environment
      --no-install-project                       Do not install the current project
      --no-install-workspace                     Do not install any workspace members, including the root project
      --no-install-package <NO_INSTALL_PACKAGE>  Do not install the given package(s)
      --locked                                   Assert that the `uv.lock` will remain unchanged [env: UV_LOCKED=]
      --frozen                                   Sync without updating the `uv.lock` file [env: UV_FROZEN=]
      --dry-run                                  Perform a dry run, without writing the lockfile or modifying the project environment
      --all-packages                             Sync all packages in the workspace
      --package <PACKAGE>                        Sync for a specific package in the workspace
      --script <SCRIPT>                          Sync the environment for a Python script, rather than the current project
      --check                                    Check if the Python environment is synchronized with the project

Index options:
      --index <INDEX>                        The URLs to use when resolving dependencies, in addition to the default index [env: UV_INDEX=]
      --default-index <DEFAULT_INDEX>        The URL of the default package index (by default: <https://pypi.org/simple>) [env: UV_DEFAULT_INDEX=]
  -i, --index-url <INDEX_URL>                (Deprecated: use `--default-index` instead) The URL of the Python package index (by default: <https://pypi.org/simple>) [env: UV_INDEX_URL=]
      --extra-index-url <EXTRA_INDEX_URL>    (Deprecated: use `--index` instead) Extra URLs of package indexes to use, in addition to `--index-url` [env: UV_EXTRA_INDEX_URL=]
  -f, --find-links <FIND_LINKS>              Locations to search for candidate distributions, in addition to those found in the registry indexes [env: UV_FIND_LINKS=]
      --no-index                             Ignore the registry index (e.g., PyPI), instead relying on direct URL dependencies and those provided via `--find-links`
      --index-strategy <INDEX_STRATEGY>      The strategy to use when resolving against multiple index URLs [env: UV_INDEX_STRATEGY=] [possible values: first-index, unsafe-first-match, unsafe-best-match]
      --keyring-provider <KEYRING_PROVIDER>  Attempt to use `keyring` for authentication for index URLs [env: UV_KEYRING_PROVIDER=] [possible values: disabled, subprocess]

Resolver options:
  -U, --upgrade                            Allow package upgrades, ignoring pinned versions in any existing output file. Implies `--refresh`
  -P, --upgrade-package <UPGRADE_PACKAGE>  Allow upgrades for a specific package, ignoring pinned versions in any existing output file. Implies `--refresh-package`
      --resolution <RESOLUTION>            The strategy to use when selecting between the different compatible versions for a given package requirement [env: UV_RESOLUTION=] [possible values: highest, lowest, lowest-direct]
      --prerelease <PRERELEASE>            The strategy to use when considering pre-release versions [env: UV_PRERELEASE=] [possible values: disallow, allow, if-necessary, explicit, if-necessary-or-explicit]
      --fork-strategy <FORK_STRATEGY>      The strategy to use when selecting multiple versions of a given package across Python versions and platforms [env: UV_FORK_STRATEGY=] [possible values: fewest, requires-python]
      --exclude-newer <EXCLUDE_NEWER>      Limit candidate packages to those that were uploaded prior to the given date [env: UV_EXCLUDE_NEWER=]
      --no-sources                         Ignore the `tool.uv.sources` table when resolving dependencies. Used to lock against the standards-compliant, publishable package metadata, as opposed to using any workspace, Git, URL, or local
                                           path sources

Installer options:
      --reinstall                              Reinstall all packages, regardless of whether they're already installed. Implies `--refresh`
      --reinstall-package <REINSTALL_PACKAGE>  Reinstall a specific package, regardless of whether it's already installed. Implies `--refresh-package`
      --link-mode <LINK_MODE>                  The method to use when installing packages from the global cache [env: UV_LINK_MODE=] [possible values: clone, copy, hardlink, symlink]
      --compile-bytecode                       Compile Python files to bytecode after installation [env: UV_COMPILE_BYTECODE=]

Build options:
  -C, --config-setting <CONFIG_SETTING>                          Settings to pass to the PEP 517 build backend, specified as `KEY=VALUE` pairs
      --no-build-isolation                                       Disable isolation when building source distributions [env: UV_NO_BUILD_ISOLATION=]
      --no-build-isolation-package <NO_BUILD_ISOLATION_PACKAGE>  Disable isolation when building source distributions for a specific package
      --no-build                                                 Don't build source distributions [env: UV_NO_BUILD=]
      --no-build-package <NO_BUILD_PACKAGE>                      Don't build source distributions for a specific package [env: UV_NO_BUILD_PACKAGE=]
      --no-binary                                                Don't install pre-built wheels [env: UV_NO_BINARY=]
      --no-binary-package <NO_BINARY_PACKAGE>                    Don't install pre-built wheels for a specific package [env: UV_NO_BINARY_PACKAGE=]

Cache options:
  -n, --no-cache                           Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation [env: UV_NO_CACHE=]
      --cache-dir <CACHE_DIR>              Path to the cache directory [env: UV_CACHE_DIR=]
      --refresh                            Refresh all cached data
      --refresh-package <REFRESH_PACKAGE>  Refresh cached data for a specific package

Python options:
  -p, --python <PYTHON>      The Python interpreter to use for the project environment. [env: UV_PYTHON=]
      --managed-python       Require use of uv-managed Python versions [env: UV_MANAGED_PYTHON=]
      --no-managed-python    Disable use of uv-managed Python versions [env: UV_NO_MANAGED_PYTHON=]
      --no-python-downloads  Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]
```

## python
```
Manage Python versions and installations

Usage: uv python [OPTIONS] <COMMAND>

Commands:
  list       List the available Python installations
  install    Download and install Python versions
  find       Search for a Python installation
  pin        Pin to a specific Python version
  dir        Show the uv Python installation directory
  uninstall  Uninstall Python versions

Python options:
      --managed-python       Require use of uv-managed Python versions [env: UV_MANAGED_PYTHON=]
      --no-managed-python    Disable use of uv-managed Python versions [env: UV_NO_MANAGED_PYTHON=]
      --no-python-downloads  Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]
```
### list
```
List the available Python installations

Usage: uv python list [OPTIONS] [REQUEST]

Arguments:
  [REQUEST]  A Python request to filter by

Options:
      --all-versions                   List all Python versions, including old patch versions
      --all-platforms                  List Python downloads for all platforms
      --all-arches                     List Python downloads for all architectures
      --only-installed                 Only show installed Python versions, exclude available downloads
      --only-downloads                 Only show Python downloads, exclude installed distributions
      --show-urls                      Show the URLs of available Python downloads
      --output-format <OUTPUT_FORMAT>  Select the output format [default: text] [possible values: text, json]
```
### install
```
Download and install Python versions

Usage: uv python install [OPTIONS] [TARGETS]...

Arguments:
  [TARGETS]...  The Python version(s) to install [env: UV_PYTHON=]

Options:
  -i, --install-dir <INSTALL_DIR>  The directory to store the Python installation in [env: UV_PYTHON_INSTALL_DIR=]
      --mirror <MIRROR>            Set the URL to use as the source for downloading Python installations [env: UV_PYTHON_INSTALL_MIRROR=]
      --pypy-mirror <PYPY_MIRROR>  Set the URL to use as the source for downloading PyPy installations [env: UV_PYPY_INSTALL_MIRROR=]
  -r, --reinstall                  Reinstall the requested Python version, if it's already installed
  -f, --force                      Replace existing Python executables during installation
      --default                    Use as the default Python version
```
### find
```
Search for a Python installation

Usage: uv python find [OPTIONS] [REQUEST]

Arguments:
  [REQUEST]  The Python request

Options:
      --no-project       Avoid discovering a project or workspace
      --system           Only find system Python interpreters [env: UV_SYSTEM_PYTHON=]
      --script <SCRIPT>  Find the environment for a Python script, rather than the current project
      --show-version     Show the Python version that would be used instead of the path to the interpreter
```
### pin
```
Pin to a specific Python version

Usage: uv python pin [OPTIONS] [REQUEST]

Arguments:
  [REQUEST]  The Python version request

Options:
      --resolved    Write the resolved Python interpreter path instead of the request
      --no-project  Avoid validating the Python pin is compatible with the project or workspace
      --global      Update the global Python version pin
```
### dir
```
Show the uv Python installation directory

Usage: uv python dir [OPTIONS]

Options:
      --bin  Show the directory into which `uv python` will install Python executables.
```
### uninstall
```
Uninstall Python versions

Usage: uv python uninstall [OPTIONS] <TARGETS>...

Arguments:
  <TARGETS>...  The Python version(s) to uninstall

Options:
  -i, --install-dir <INSTALL_DIR>  The directory where the Python was installed [env: UV_PYTHON_INSTALL_DIR=]
      --all                        Uninstall all managed Python versions
```


## pip
```
Manage Python packages with a pip-compatible interface

Usage: uv pip [OPTIONS] <COMMAND>

Commands:
  compile    Compile a `requirements.in` file to a `requirements.txt` file
  sync       Sync an environment with a `requirements.txt` file
  install    Install packages into an environment
  uninstall  Uninstall packages from an environment
  freeze     List, in requirements format, packages installed in an environment
  list       List, in tabular format, packages installed in an environment
  show       Show information about one or more installed packages
  tree       Display the dependency tree for an environment
  check      Verify installed packages have compatible dependencies

Python options:
      --managed-python       Require use of uv-managed Python versions [env: UV_MANAGED_PYTHON=]
      --no-managed-python    Disable use of uv-managed Python versions [env: UV_NO_MANAGED_PYTHON=]
      --no-python-downloads  Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]
```
### install
```
Install packages into an environment

Usage: uv pip install [OPTIONS] <PACKAGE|--requirements <REQUIREMENTS>|--editable <EDITABLE>|--group <GROUP>>

Arguments:
  [PACKAGE]...  Install all listed packages

Options:
  -r, --requirements <REQUIREMENTS>            Install all packages listed in the given `requirements.txt` files
  -e, --editable <EDITABLE>                    Install the editable package based on the provided local file path
  -c, --constraints <CONSTRAINTS>              Constrain versions using the given requirements files [env: UV_CONSTRAINT=]
      --overrides <OVERRIDES>                  Override versions using the given requirements files [env: UV_OVERRIDE=]
  -b, --build-constraints <BUILD_CONSTRAINTS>  Constrain build dependencies using the given requirements files when building source distributions [env: UV_BUILD_CONSTRAINT=]
      --extra <EXTRA>                          Include optional dependencies from the specified extra name; may be provided more than once
      --all-extras                             Include all optional dependencies
      --no-deps                                Ignore package dependencies, instead only installing those packages explicitly listed on the command line or in the requirements files
      --group <GROUP>                          Install the specified dependency group from a `pyproject.toml`
      --require-hashes                         Require a matching hash for each requirement [env: UV_REQUIRE_HASHES=]
      --no-verify-hashes                       Disable validation of hashes in the requirements file [env: UV_NO_VERIFY_HASHES=]
      --system                                 Install packages into the system Python environment [env: UV_SYSTEM_PYTHON=]
      --break-system-packages                  Allow uv to modify an `EXTERNALLY-MANAGED` Python installation [env: UV_BREAK_SYSTEM_PACKAGES=]
      --no-break-system-packages               
      --target <TARGET>                        Install packages into the specified directory, rather than into the virtual or system Python environment. The packages will be installed at the top-level of the directory
      --prefix <PREFIX>                        Install packages into `lib`, `bin`, and other top-level folders under the specified directory, as if a virtual environment were present at that location
      --no-build                               Don't build source distributions
      --no-binary <NO_BINARY>                  Don't install pre-built wheels
      --only-binary <ONLY_BINARY>              Only use pre-built wheels; don't build source distributions
      --python-version <PYTHON_VERSION>        The minimum Python version that should be supported by the requirements (e.g., `3.7` or `3.7.9`)
      --python-platform <PYTHON_PLATFORM>      The platform for which requirements should be installed [possible values: windows, linux, macos, x86_64-pc-windows-msvc, i686-pc-windows-msvc, x86_64-unknown-linux-gnu,
                                               aarch64-apple-darwin, x86_64-apple-darwin, aarch64-unknown-linux-gnu, aarch64-unknown-linux-musl, x86_64-unknown-linux-musl, x86_64-manylinux2014, x86_64-manylinux_2_17,
                                               x86_64-manylinux_2_28, x86_64-manylinux_2_31, x86_64-manylinux_2_32, x86_64-manylinux_2_33, x86_64-manylinux_2_34, x86_64-manylinux_2_35, x86_64-manylinux_2_36, x86_64-manylinux_2_37,
                                               x86_64-manylinux_2_38, x86_64-manylinux_2_39, x86_64-manylinux_2_40, aarch64-manylinux2014, aarch64-manylinux_2_17, aarch64-manylinux_2_28, aarch64-manylinux_2_31, aarch64-manylinux_2_32,
                                               aarch64-manylinux_2_33, aarch64-manylinux_2_34, aarch64-manylinux_2_35, aarch64-manylinux_2_36, aarch64-manylinux_2_37, aarch64-manylinux_2_38, aarch64-manylinux_2_39,
                                               aarch64-manylinux_2_40]
      --exact                                  Perform an exact sync, removing extraneous packages
      --strict                                 Validate the Python environment after completing the installation, to detect packages with missing dependencies or other issues
      --dry-run                                Perform a dry run, i.e., don't actually install anything but resolve the dependencies and print the resulting plan
      --torch-backend <TORCH_BACKEND>          The backend to use when fetching packages in the PyTorch ecosystem (e.g., `cpu`, `cu126`, or `auto`) [env: UV_TORCH_BACKEND=] [possible values: auto, cpu, cu126, cu125, cu124, cu123, cu122,
                                               cu121, cu120, cu118, cu117, cu116, cu115, cu114, cu113, cu112, cu111, cu110, cu102, cu101, cu100, cu92, cu91, cu90, cu80]
      --user                                   

Index options:
      --index <INDEX>                        The URLs to use when resolving dependencies, in addition to the default index [env: UV_INDEX=]
      --default-index <DEFAULT_INDEX>        The URL of the default package index (by default: <https://pypi.org/simple>) [env: UV_DEFAULT_INDEX=]
  -i, --index-url <INDEX_URL>                (Deprecated: use `--default-index` instead) The URL of the Python package index (by default: <https://pypi.org/simple>) [env: UV_INDEX_URL=]
      --extra-index-url <EXTRA_INDEX_URL>    (Deprecated: use `--index` instead) Extra URLs of package indexes to use, in addition to `--index-url` [env: UV_EXTRA_INDEX_URL=]
  -f, --find-links <FIND_LINKS>              Locations to search for candidate distributions, in addition to those found in the registry indexes [env: UV_FIND_LINKS=]
      --no-index                             Ignore the registry index (e.g., PyPI), instead relying on direct URL dependencies and those provided via `--find-links`
      --index-strategy <INDEX_STRATEGY>      The strategy to use when resolving against multiple index URLs [env: UV_INDEX_STRATEGY=] [possible values: first-index, unsafe-first-match, unsafe-best-match]
      --keyring-provider <KEYRING_PROVIDER>  Attempt to use `keyring` for authentication for index URLs [env: UV_KEYRING_PROVIDER=] [possible values: disabled, subprocess]

Resolver options:
  -U, --upgrade                            Allow package upgrades, ignoring pinned versions in any existing output file. Implies `--refresh`
  -P, --upgrade-package <UPGRADE_PACKAGE>  Allow upgrades for a specific package, ignoring pinned versions in any existing output file. Implies `--refresh-package`
      --resolution <RESOLUTION>            The strategy to use when selecting between the different compatible versions for a given package requirement [env: UV_RESOLUTION=] [possible values: highest, lowest, lowest-direct]
      --prerelease <PRERELEASE>            The strategy to use when considering pre-release versions [env: UV_PRERELEASE=] [possible values: disallow, allow, if-necessary, explicit, if-necessary-or-explicit]
      --fork-strategy <FORK_STRATEGY>      The strategy to use when selecting multiple versions of a given package across Python versions and platforms [env: UV_FORK_STRATEGY=] [possible values: fewest, requires-python]
      --exclude-newer <EXCLUDE_NEWER>      Limit candidate packages to those that were uploaded prior to the given date [env: UV_EXCLUDE_NEWER=]
      --no-sources                         Ignore the `tool.uv.sources` table when resolving dependencies. Used to lock against the standards-compliant, publishable package metadata, as opposed to using any workspace, Git, URL, or local
                                           path sources

Installer options:
      --reinstall                              Reinstall all packages, regardless of whether they're already installed. Implies `--refresh`
      --reinstall-package <REINSTALL_PACKAGE>  Reinstall a specific package, regardless of whether it's already installed. Implies `--refresh-package`
      --link-mode <LINK_MODE>                  The method to use when installing packages from the global cache [env: UV_LINK_MODE=] [possible values: clone, copy, hardlink, symlink]
      --compile-bytecode                       Compile Python files to bytecode after installation [env: UV_COMPILE_BYTECODE=]

Build options:
  -C, --config-setting <CONFIG_SETTING>                          Settings to pass to the PEP 517 build backend, specified as `KEY=VALUE` pairs
      --no-build-isolation                                       Disable isolation when building source distributions [env: UV_NO_BUILD_ISOLATION=]
      --no-build-isolation-package <NO_BUILD_ISOLATION_PACKAGE>  Disable isolation when building source distributions for a specific package

Cache options:
  -n, --no-cache                           Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation [env: UV_NO_CACHE=]
      --cache-dir <CACHE_DIR>              Path to the cache directory [env: UV_CACHE_DIR=]
      --refresh                            Refresh all cached data
      --refresh-package <REFRESH_PACKAGE>  Refresh cached data for a specific package

Python options:
  -p, --python <PYTHON>      The Python interpreter into which packages should be installed. [env: UV_PYTHON=]
      --managed-python       Require use of uv-managed Python versions [env: UV_MANAGED_PYTHON=]
      --no-managed-python    Disable use of uv-managed Python versions [env: UV_NO_MANAGED_PYTHON=]
      --no-python-downloads  Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]
```


## venv
```
Create a virtual environment

Usage: uv venv [OPTIONS] [PATH]

Arguments:
  [PATH]  The path to the virtual environment to create

Options:
      --no-project                           Avoid discovering a project or workspace
      --seed                                 Install seed packages (one or more of: `pip`, `setuptools`, and `wheel`) into the virtual environment [env: UV_VENV_SEED=]
      --allow-existing                       Preserve any existing files or directories at the target path
      --prompt <PROMPT>                      Provide an alternative prompt prefix for the virtual environment.
      --system-site-packages                 Give the virtual environment access to the system site packages directory
      --relocatable                          Make the virtual environment relocatable
      --index-strategy <INDEX_STRATEGY>      The strategy to use when resolving against multiple index URLs [env: UV_INDEX_STRATEGY=] [possible values: first-index, unsafe-first-match, unsafe-best-match]
      --keyring-provider <KEYRING_PROVIDER>  Attempt to use `keyring` for authentication for index URLs [env: UV_KEYRING_PROVIDER=] [possible values: disabled, subprocess]
      --exclude-newer <EXCLUDE_NEWER>        Limit candidate packages to those that were uploaded prior to the given date [env: UV_EXCLUDE_NEWER=]
      --link-mode <LINK_MODE>                The method to use when installing packages from the global cache [env: UV_LINK_MODE=] [possible values: clone, copy, hardlink, symlink]

Python options:
  -p, --python <PYTHON>      The Python interpreter to use for the virtual environment. [env: UV_PYTHON=]
      --managed-python       Require use of uv-managed Python versions [env: UV_MANAGED_PYTHON=]
      --no-managed-python    Disable use of uv-managed Python versions [env: UV_NO_MANAGED_PYTHON=]
      --no-python-downloads  Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]

Index options:
      --index <INDEX>                      The URLs to use when resolving dependencies, in addition to the default index [env: UV_INDEX=]
      --default-index <DEFAULT_INDEX>      The URL of the default package index (by default: <https://pypi.org/simple>) [env: UV_DEFAULT_INDEX=]
  -i, --index-url <INDEX_URL>              (Deprecated: use `--default-index` instead) The URL of the Python package index (by default: <https://pypi.org/simple>) [env: UV_INDEX_URL=]
      --extra-index-url <EXTRA_INDEX_URL>  (Deprecated: use `--index` instead) Extra URLs of package indexes to use, in addition to `--index-url` [env: UV_EXTRA_INDEX_URL=]
  -f, --find-links <FIND_LINKS>            Locations to search for candidate distributions, in addition to those found in the registry indexes [env: UV_FIND_LINKS=]
      --no-index                           Ignore the registry index (e.g., PyPI), instead relying on direct URL dependencies and those provided via `--find-links`
```
