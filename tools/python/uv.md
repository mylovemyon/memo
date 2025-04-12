https://github.com/astral-sh/uv
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

Cache options:
  -n, --no-cache               Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation [env: UV_NO_CACHE=]
      --cache-dir <CACHE_DIR>  Path to the cache directory [env: UV_CACHE_DIR=]

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
```


## add
```
sage: uv add [OPTIONS] <PACKAGES|--requirements <REQUIREMENTS>>

Arguments:
  [PACKAGES]...  The packages to add, as PEP 508 requirements (e.g., `ruff==0.5.0`)

Options:
  -r, --requirements <REQUIREMENTS>  Add all packages listed in the given `requirements.txt` files
  -c, --constraints <CONSTRAINTS>    Constrain versions using the given requirements files [env: UV_CONSTRAINT=]
  -m, --marker <MARKER>              Apply this marker to all added packages
      --dev                          Add the requirements to the development dependency group
      --optional <OPTIONAL>          Add the requirements to the package's optional dependencies for the specified extra
      --group <GROUP>                Add the requirements to the specified dependency group
      --editable                     Add the requirements as editable
      --raw-sources                  Add source requirements to `project.dependencies`, rather than `tool.uv.sources`
      --rev <REV>                    Commit to use when adding a dependency from Git
      --tag <TAG>                    Tag to use when adding a dependency from Git
      --branch <BRANCH>              Branch to use when adding a dependency from Git
      --extra <EXTRA>                Extras to enable for the dependency
      --no-sync                      Avoid syncing the virtual environment [env: UV_NO_SYNC=]
      --locked                       Assert that the `uv.lock` will remain unchanged [env: UV_LOCKED=]
      --frozen                       Add dependencies without re-locking the project [env: UV_FROZEN=]
      --active                       Prefer the active virtual environment over the project's virtual environment
      --package <PACKAGE>            Add the dependency to a specific package in the workspace
      --script <SCRIPT>              Add the dependency to the specified Python script, rather than to a project

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
      --no-sources                         Ignore the `tool.uv.sources` table when resolving dependencies. Used to lock against the standards-compliant, publishable package metadata, as opposed to using any workspace, Git, URL, or
                                           local path sources

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
  -p, --python <PYTHON>      The Python interpreter to use for resolving and syncing. [env: UV_PYTHON=]
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

Use `uv help add` for more details.
```
