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
  [PATH]
          The path to use for the project/script.
          
          Defaults to the current working directory when initializing an app or library; required when initializing a script. Accepts relative and absolute paths.
          
          If a `pyproject.toml` is found in any of the parent directories of the target path, the project will be added as a workspace member of the parent, unless `--no-workspace` is provided.

Options:
      --name <NAME>
          The name of the project.
          
          Defaults to the name of the directory.

      --bare
          Only create a `pyproject.toml`.
          
          Disables creating extra files like `README.md`, the `src/` tree, `.python-version` files, etc.

      --package
          Set up the project to be built as a Python package.
          
          Defines a `[build-system]` for the project.
          
          This is the default behavior when using `--lib` or `--build-backend`.
          
          When using `--app`, this will include a `[project.scripts]` entrypoint and use a `src/` project structure.

      --no-package
          Do not set up the project to be built as a Python package.
          
          Does not include a `[build-system]` for the project.
          
          This is the default behavior when using `--app`.

      --app
          Create a project for an application.
          
          This is the default behavior if `--lib` is not requested.
          
          This project kind is for web servers, scripts, and command-line interfaces.
          
          By default, an application is not intended to be built and distributed as a Python package. The `--package` option can be used to create an application that is distributable, e.g., if you want to distribute a command-line
          interface via PyPI.

      --lib
          Create a project for a library.
          
          A library is a project that is intended to be built and distributed as a Python package.

      --script
          Create a script.
          
          A script is a standalone file with embedded metadata enumerating its dependencies, along with any Python version requirements, as defined in the PEP 723 specification.
          
          PEP 723 scripts can be executed directly with `uv run`.
          
          By default, adds a requirement on the system Python version; use `--python` to specify an alternative Python version requirement.

      --description <DESCRIPTION>
          Set the project description

      --no-description
          Disable the description for the project

      --vcs <VCS>
          Initialize a version control system for the project.
          
          By default, uv will initialize a Git repository (`git`). Use `--vcs none` to explicitly avoid initializing a version control system.

          Possible values:
          - git:  Use Git for version control
          - none: Do not use any version control system

      --build-backend <BUILD_BACKEND>
          Initialize a build-backend of choice for the project.
          
          Implicitly sets `--package`.

          Possible values:
          - hatch:      Use [hatchling](https://pypi.org/project/hatchling) as the project build backend
          - flit:       Use [flit-core](https://pypi.org/project/flit-core) as the project build backend
          - pdm:        Use [pdm-backend](https://pypi.org/project/pdm-backend) as the project build backend
          - setuptools: Use [setuptools](https://pypi.org/project/setuptools) as the project build backend
          - maturin:    Use [maturin](https://pypi.org/project/maturin) as the project build backend
          - scikit:     Use [scikit-build-core](https://pypi.org/project/scikit-build-core) as the project build backend

      --no-readme
          Do not create a `README.md` file

      --author-from <AUTHOR_FROM>
          Fill in the `authors` field in the `pyproject.toml`.
          
          By default, uv will attempt to infer the author information from some sources (e.g., Git) (`auto`). Use `--author-from git` to only infer from Git configuration. Use `--author-from none` to avoid inferring the author
          information.

          Possible values:
          - auto: Fetch the author information from some sources (e.g., Git) automatically
          - git:  Fetch the author information from Git configuration only
          - none: Do not infer the author information

      --no-pin-python
          Do not create a `.python-version` file for the project.
          
          By default, uv will create a `.python-version` file containing the minor version of the discovered Python interpreter, which will cause subsequent uv commands to use that version.

      --no-workspace
          Avoid discovering a workspace and create a standalone project.
          
          By default, uv searches for workspaces in the current directory or any parent directory.

Python options:
  -p, --python <PYTHON>
          The Python interpreter to use to determine the minimum supported Python version.
          
          See `uv help python` to view supported request formats.
          
          [env: UV_PYTHON=]

      --managed-python
          Require use of uv-managed Python versions.
          
          By default, uv prefers using Python versions it manages. However, it will use system Python versions if a uv-managed Python is not installed. This option disables use of system Python versions.
          
          [env: UV_MANAGED_PYTHON=]

      --no-managed-python
          Disable use of uv-managed Python versions.
          
          Instead, uv will search for a suitable Python version on the system.
          
          [env: UV_NO_MANAGED_PYTHON=]

      --no-python-downloads
          Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]

Cache options:
  -n, --no-cache
          Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation
          
          [env: UV_NO_CACHE=]

      --cache-dir <CACHE_DIR>
          Path to the cache directory.
          
          Defaults to `$XDG_CACHE_HOME/uv` or `$HOME/.cache/uv` on macOS and Linux, and `%LOCALAPPDATA%\uv\cache` on Windows.
          
          To view the location of the cache directory, run `uv cache dir`.
          
          [env: UV_CACHE_DIR=]

Global options:
  -q, --quiet...
          Use quiet output.
          
          Repeating this option, e.g., `-qq`, will enable a silent mode in which uv will write no output to stdout.

  -v, --verbose...
          Use verbose output.
          
          You can configure fine-grained logging using the `RUST_LOG` environment variable. (<https://docs.rs/tracing-subscriber/latest/tracing_subscriber/filter/struct.EnvFilter.html#directives>)

      --color <COLOR_CHOICE>
          Control the use of color in output.
          
          By default, uv will automatically detect support for colors when writing to a terminal.

          Possible values:
          - auto:   Enables colored output only when the output is going to a terminal or TTY with support
          - always: Enables colored output regardless of the detected environment
          - never:  Disables colored output

      --native-tls
          Whether to load TLS certificates from the platform's native certificate store.
          
          By default, uv loads certificates from the bundled `webpki-roots` crate. The `webpki-roots` are a reliable set of trust roots from Mozilla, and including them in uv improves portability and performance (especially on macOS).
          
          However, in some cases, you may want to use the platform's native certificate store, especially if you're relying on a corporate trust root (e.g., for a mandatory proxy) that's included in your system's certificate store.
          
          [env: UV_NATIVE_TLS=]

      --offline
          Disable network access.
          
          When disabled, uv will only use locally cached data and locally available files.
          
          [env: UV_OFFLINE=]

      --allow-insecure-host <ALLOW_INSECURE_HOST>
          Allow insecure connections to a host.
          
          Can be provided multiple times.
          
          Expects to receive either a hostname (e.g., `localhost`), a host-port pair (e.g., `localhost:8080`), or a URL (e.g., `https://localhost`).
          
          WARNING: Hosts included in this list will not be verified against the system's certificate store. Only use `--allow-insecure-host` in a secure network with verified sources, as it bypasses SSL verification and could expose
          you to MITM attacks.
          
          [env: UV_INSECURE_HOST=]

      --no-progress
          Hide all progress outputs.
          
          For example, spinners or progress bars.
          
          [env: UV_NO_PROGRESS=]

      --directory <DIRECTORY>
          Change to the given directory prior to running the command.
          
          Relative paths are resolved with the given directory as the base.
          
          See `--project` to only change the project root directory.

      --project <PROJECT>
          Run the command within the given project directory.
          
          All `pyproject.toml`, `uv.toml`, and `.python-version` files will be discovered by walking up the directory tree from the project root, as will the project's virtual environment (`.venv`).
          
          Other command-line arguments (such as relative paths) will be resolved relative to the current working directory.
          
          See `--directory` to change the working directory entirely.
          
          This setting has no effect when used in the `uv pip` interface.
          
          [env: UV_PROJECT=]

      --config-file <CONFIG_FILE>
          The path to a `uv.toml` file to use for configuration.
          
          While uv configuration can be included in a `pyproject.toml` file, it is not allowed in this context.
          
          [env: UV_CONFIG_FILE=]

      --no-config
          Avoid discovering configuration files (`pyproject.toml`, `uv.toml`).
          
          Normally, configuration files are discovered in the current directory, parent directories, or user configuration directories.
          
          [env: UV_NO_CONFIG=]

  -h, --help
          Display the concise help for this command

  -V, --version
          Display the uv version
```


## add
```
Add dependencies to the project.

Dependencies are added to the project's `pyproject.toml` file.

If a given dependency exists already, it will be updated to the new version specifier unless it includes markers that differ from the existing specifier in which case another entry for the dependency will be added.

If no constraint or URL is provided for a dependency, a lower bound is added equal to the latest compatible version of the package, e.g., `>=1.2.3`, unless `--frozen` is provided, in which case no resolution is performed.

The lockfile and project environment will be updated to reflect the added dependencies. To skip updating the lockfile, use `--frozen`. To skip updating the environment, use `--no-sync`.

If any of the requested dependencies cannot be found, uv will exit with an error, unless the `--frozen` flag is provided, in which case uv will add the dependencies verbatim without checking that they exist or are compatible with the
project.

uv will search for a project in the current directory or any parent directory. If a project cannot be found, uv will exit with an error.

Usage: uv add [OPTIONS] <PACKAGES|--requirements <REQUIREMENTS>>

Arguments:
  [PACKAGES]...
          The packages to add, as PEP 508 requirements (e.g., `ruff==0.5.0`)

Options:
  -r, --requirements <REQUIREMENTS>
          Add all packages listed in the given `requirements.txt` files

  -c, --constraints <CONSTRAINTS>
          Constrain versions using the given requirements files.
          
          Constraints files are `requirements.txt`-like files that only control the _version_ of a requirement that's installed. The constraints will _not_ be added to the project's `pyproject.toml` file, but _will_ be respected during
          dependency resolution.
          
          This is equivalent to pip's `--constraint` option.
          
          [env: UV_CONSTRAINT=]

  -m, --marker <MARKER>
          Apply this marker to all added packages

      --dev
          Add the requirements to the development dependency group.
          
          This option is an alias for `--group dev`.

      --optional <OPTIONAL>
          Add the requirements to the package's optional dependencies for the specified extra.
          
          The group may then be activated when installing the project with the `--extra` flag.
          
          To enable an optional extra for this requirement instead, see `--extra`.

      --group <GROUP>
          Add the requirements to the specified dependency group.
          
          These requirements will not be included in the published metadata for the project.

      --editable
          Add the requirements as editable

      --raw-sources
          Add source requirements to `project.dependencies`, rather than `tool.uv.sources`.
          
          By default, uv will use the `tool.uv.sources` section to record source information for Git, local, editable, and direct URL requirements.

      --rev <REV>
          Commit to use when adding a dependency from Git

      --tag <TAG>
          Tag to use when adding a dependency from Git

      --branch <BRANCH>
          Branch to use when adding a dependency from Git

      --extra <EXTRA>
          Extras to enable for the dependency.
          
          May be provided more than once.
          
          To add this dependency to an optional extra instead, see `--optional`.

      --no-sync
          Avoid syncing the virtual environment
          
          [env: UV_NO_SYNC=]

      --locked
          Assert that the `uv.lock` will remain unchanged.
          
          Requires that the lockfile is up-to-date. If the lockfile is missing or needs to be updated, uv will exit with an error.
          
          [env: UV_LOCKED=]

      --frozen
          Add dependencies without re-locking the project.
          
          The project environment will not be synced.
          
          [env: UV_FROZEN=]

      --active
          Prefer the active virtual environment over the project's virtual environment.
          
          If the project virtual environment is active or no virtual environment is active, this has no effect.

      --package <PACKAGE>
          Add the dependency to a specific package in the workspace

      --script <SCRIPT>
          Add the dependency to the specified Python script, rather than to a project.
          
          If provided, uv will add the dependency to the script's inline metadata table, in adherence with PEP 723. If no such inline metadata table is present, a new one will be created and added to the script. When executed via `uv
          run`, uv will create a temporary environment for the script with all inline dependencies installed.

Index options:
      --index <INDEX>
          The URLs to use when resolving dependencies, in addition to the default index.
          
          Accepts either a repository compliant with PEP 503 (the simple repository API), or a local directory laid out in the same format.
          
          All indexes provided via this flag take priority over the index specified by `--default-index` (which defaults to PyPI). When multiple `--index` flags are provided, earlier values take priority.
          
          [env: UV_INDEX=]

      --default-index <DEFAULT_INDEX>
          The URL of the default package index (by default: <https://pypi.org/simple>).
          
          Accepts either a repository compliant with PEP 503 (the simple repository API), or a local directory laid out in the same format.
          
          The index given by this flag is given lower priority than all other indexes specified via the `--index` flag.
          
          [env: UV_DEFAULT_INDEX=]

  -i, --index-url <INDEX_URL>
          (Deprecated: use `--default-index` instead) The URL of the Python package index (by default: <https://pypi.org/simple>).
          
          Accepts either a repository compliant with PEP 503 (the simple repository API), or a local directory laid out in the same format.
          
          The index given by this flag is given lower priority than all other indexes specified via the `--extra-index-url` flag.
          
          [env: UV_INDEX_URL=]

      --extra-index-url <EXTRA_INDEX_URL>
          (Deprecated: use `--index` instead) Extra URLs of package indexes to use, in addition to `--index-url`.
          
          Accepts either a repository compliant with PEP 503 (the simple repository API), or a local directory laid out in the same format.
          
          All indexes provided via this flag take priority over the index specified by `--index-url` (which defaults to PyPI). When multiple `--extra-index-url` flags are provided, earlier values take priority.
          
          [env: UV_EXTRA_INDEX_URL=]

  -f, --find-links <FIND_LINKS>
          Locations to search for candidate distributions, in addition to those found in the registry indexes.
          
          If a path, the target must be a directory that contains packages as wheel files (`.whl`) or source distributions (e.g., `.tar.gz` or `.zip`) at the top level.
          
          If a URL, the page must contain a flat list of links to package files adhering to the formats described above.
          
          [env: UV_FIND_LINKS=]

      --no-index
          Ignore the registry index (e.g., PyPI), instead relying on direct URL dependencies and those provided via `--find-links`

      --index-strategy <INDEX_STRATEGY>
          The strategy to use when resolving against multiple index URLs.
          
          By default, uv will stop at the first index on which a given package is available, and limit resolutions to those present on that first index (`first-index`). This prevents "dependency confusion" attacks, whereby an attacker
          can upload a malicious package under the same name to an alternate index.
          
          [env: UV_INDEX_STRATEGY=]

          Possible values:
          - first-index:        Only use results from the first index that returns a match for a given package name
          - unsafe-first-match: Search for every package name across all indexes, exhausting the versions from the first index before moving on to the next
          - unsafe-best-match:  Search for every package name across all indexes, preferring the "best" version found. If a package version is in multiple indexes, only look at the entry for the first index

      --keyring-provider <KEYRING_PROVIDER>
          Attempt to use `keyring` for authentication for index URLs.
          
          At present, only `--keyring-provider subprocess` is supported, which configures uv to use the `keyring` CLI to handle authentication.
          
          Defaults to `disabled`.
          
          [env: UV_KEYRING_PROVIDER=]

          Possible values:
          - disabled:   Do not use keyring for credential lookup
          - subprocess: Use the `keyring` command for credential lookup

Resolver options:
  -U, --upgrade
          Allow package upgrades, ignoring pinned versions in any existing output file. Implies `--refresh`

  -P, --upgrade-package <UPGRADE_PACKAGE>
          Allow upgrades for a specific package, ignoring pinned versions in any existing output file. Implies `--refresh-package`

      --resolution <RESOLUTION>
          The strategy to use when selecting between the different compatible versions for a given package requirement.
          
          By default, uv will use the latest compatible version of each package (`highest`).
          
          [env: UV_RESOLUTION=]

          Possible values:
          - highest:       Resolve the highest compatible version of each package
          - lowest:        Resolve the lowest compatible version of each package
          - lowest-direct: Resolve the lowest compatible version of any direct dependencies, and the highest compatible version of any transitive dependencies

      --prerelease <PRERELEASE>
          The strategy to use when considering pre-release versions.
          
          By default, uv will accept pre-releases for packages that _only_ publish pre-releases, along with first-party requirements that contain an explicit pre-release marker in the declared specifiers (`if-necessary-or-explicit`).
          
          [env: UV_PRERELEASE=]

          Possible values:
          - disallow:                 Disallow all pre-release versions
          - allow:                    Allow all pre-release versions
          - if-necessary:             Allow pre-release versions if all versions of a package are pre-release
          - explicit:                 Allow pre-release versions for first-party packages with explicit pre-release markers in their version requirements
          - if-necessary-or-explicit: Allow pre-release versions if all versions of a package are pre-release, or if the package has an explicit pre-release marker in its version requirements

      --fork-strategy <FORK_STRATEGY>
          The strategy to use when selecting multiple versions of a given package across Python versions and platforms.
          
          By default, uv will optimize for selecting the latest version of each package for each supported Python version (`requires-python`), while minimizing the number of selected versions across platforms.
          
          Under `fewest`, uv will minimize the number of selected versions for each package, preferring older versions that are compatible with a wider range of supported Python versions or platforms.
          
          [env: UV_FORK_STRATEGY=]

          Possible values:
          - fewest:          Optimize for selecting the fewest number of versions for each package. Older versions may be preferred if they are compatible with a wider range of supported Python versions or platforms
          - requires-python: Optimize for selecting latest supported version of each package, for each supported Python version

      --exclude-newer <EXCLUDE_NEWER>
          Limit candidate packages to those that were uploaded prior to the given date.
          
          Accepts both RFC 3339 timestamps (e.g., `2006-12-02T02:07:43Z`) and local dates in the same format (e.g., `2006-12-02`) in your system's configured time zone.
          
          [env: UV_EXCLUDE_NEWER=]

      --no-sources
          Ignore the `tool.uv.sources` table when resolving dependencies. Used to lock against the standards-compliant, publishable package metadata, as opposed to using any workspace, Git, URL, or local path sources

Installer options:
      --reinstall
          Reinstall all packages, regardless of whether they're already installed. Implies `--refresh`

      --reinstall-package <REINSTALL_PACKAGE>
          Reinstall a specific package, regardless of whether it's already installed. Implies `--refresh-package`

      --link-mode <LINK_MODE>
          The method to use when installing packages from the global cache.
          
          Defaults to `clone` (also known as Copy-on-Write) on macOS, and `hardlink` on Linux and Windows.
          
          [env: UV_LINK_MODE=]

          Possible values:
          - clone:    Clone (i.e., copy-on-write) packages from the wheel into the `site-packages` directory
          - copy:     Copy packages from the wheel into the `site-packages` directory
          - hardlink: Hard link packages from the wheel into the `site-packages` directory
          - symlink:  Symbolically link packages from the wheel into the `site-packages` directory

      --compile-bytecode
          Compile Python files to bytecode after installation.
          
          By default, uv does not compile Python (`.py`) files to bytecode (`__pycache__/*.pyc`); instead, compilation is performed lazily the first time a module is imported. For use-cases in which start time is critical, such as CLI
          applications and Docker containers, this option can be enabled to trade longer installation times for faster start times.
          
          When enabled, uv will process the entire site-packages directory (including packages that are not being modified by the current operation) for consistency. Like pip, it will also ignore errors.
          
          [env: UV_COMPILE_BYTECODE=]

Build options:
  -C, --config-setting <CONFIG_SETTING>
          Settings to pass to the PEP 517 build backend, specified as `KEY=VALUE` pairs

      --no-build-isolation
          Disable isolation when building source distributions.
          
          Assumes that build dependencies specified by PEP 518 are already installed.
          
          [env: UV_NO_BUILD_ISOLATION=]

      --no-build-isolation-package <NO_BUILD_ISOLATION_PACKAGE>
          Disable isolation when building source distributions for a specific package.
          
          Assumes that the packages' build dependencies specified by PEP 518 are already installed.

      --no-build
          Don't build source distributions.
          
          When enabled, resolving will not run arbitrary Python code. The cached wheels of already-built source distributions will be reused, but operations that require building distributions will exit with an error.
          
          [env: UV_NO_BUILD=]

      --no-build-package <NO_BUILD_PACKAGE>
          Don't build source distributions for a specific package
          
          [env: UV_NO_BUILD_PACKAGE=]

      --no-binary
          Don't install pre-built wheels.
          
          The given packages will be built and installed from source. The resolver will still use pre-built wheels to extract package metadata, if available.
          
          [env: UV_NO_BINARY=]

      --no-binary-package <NO_BINARY_PACKAGE>
          Don't install pre-built wheels for a specific package
          
          [env: UV_NO_BINARY_PACKAGE=]

Cache options:
  -n, --no-cache
          Avoid reading from or writing to the cache, instead using a temporary directory for the duration of the operation
          
          [env: UV_NO_CACHE=]

      --cache-dir <CACHE_DIR>
          Path to the cache directory.
          
          Defaults to `$XDG_CACHE_HOME/uv` or `$HOME/.cache/uv` on macOS and Linux, and `%LOCALAPPDATA%\uv\cache` on Windows.
          
          To view the location of the cache directory, run `uv cache dir`.
          
          [env: UV_CACHE_DIR=]

      --refresh
          Refresh all cached data

      --refresh-package <REFRESH_PACKAGE>
          Refresh cached data for a specific package

Python options:
  -p, --python <PYTHON>
          The Python interpreter to use for resolving and syncing.
          
          See `uv help python` for details on Python discovery and supported request formats.
          
          [env: UV_PYTHON=]

      --managed-python
          Require use of uv-managed Python versions.
          
          By default, uv prefers using Python versions it manages. However, it will use system Python versions if a uv-managed Python is not installed. This option disables use of system Python versions.
          
          [env: UV_MANAGED_PYTHON=]

      --no-managed-python
          Disable use of uv-managed Python versions.
          
          Instead, uv will search for a suitable Python version on the system.
          
          [env: UV_NO_MANAGED_PYTHON=]

      --no-python-downloads
          Disable automatic downloads of Python. [env: "UV_PYTHON_DOWNLOADS=never"]

Global options:
  -q, --quiet...
          Use quiet output.
          
          Repeating this option, e.g., `-qq`, will enable a silent mode in which uv will write no output to stdout.

  -v, --verbose...
          Use verbose output.
          
          You can configure fine-grained logging using the `RUST_LOG` environment variable. (<https://docs.rs/tracing-subscriber/latest/tracing_subscriber/filter/struct.EnvFilter.html#directives>)

      --color <COLOR_CHOICE>
          Control the use of color in output.
          
          By default, uv will automatically detect support for colors when writing to a terminal.

          Possible values:
          - auto:   Enables colored output only when the output is going to a terminal or TTY with support
          - always: Enables colored output regardless of the detected environment
          - never:  Disables colored output

      --native-tls
          Whether to load TLS certificates from the platform's native certificate store.
          
          By default, uv loads certificates from the bundled `webpki-roots` crate. The `webpki-roots` are a reliable set of trust roots from Mozilla, and including them in uv improves portability and performance (especially on macOS).
          
          However, in some cases, you may want to use the platform's native certificate store, especially if you're relying on a corporate trust root (e.g., for a mandatory proxy) that's included in your system's certificate store.
          
          [env: UV_NATIVE_TLS=]

      --offline
          Disable network access.
          
          When disabled, uv will only use locally cached data and locally available files.
          
          [env: UV_OFFLINE=]

      --allow-insecure-host <ALLOW_INSECURE_HOST>
          Allow insecure connections to a host.
          
          Can be provided multiple times.
          
          Expects to receive either a hostname (e.g., `localhost`), a host-port pair (e.g., `localhost:8080`), or a URL (e.g., `https://localhost`).
          
          WARNING: Hosts included in this list will not be verified against the system's certificate store. Only use `--allow-insecure-host` in a secure network with verified sources, as it bypasses SSL verification and could expose
          you to MITM attacks.
          
          [env: UV_INSECURE_HOST=]

      --no-progress
          Hide all progress outputs.
          
          For example, spinners or progress bars.
          
          [env: UV_NO_PROGRESS=]

      --directory <DIRECTORY>
          Change to the given directory prior to running the command.
          
          Relative paths are resolved with the given directory as the base.
          
          See `--project` to only change the project root directory.

      --project <PROJECT>
          Run the command within the given project directory.
          
          All `pyproject.toml`, `uv.toml`, and `.python-version` files will be discovered by walking up the directory tree from the project root, as will the project's virtual environment (`.venv`).
          
          Other command-line arguments (such as relative paths) will be resolved relative to the current working directory.
          
          See `--directory` to change the working directory entirely.
          
          This setting has no effect when used in the `uv pip` interface.
          
          [env: UV_PROJECT=]

      --config-file <CONFIG_FILE>
          The path to a `uv.toml` file to use for configuration.
          
          While uv configuration can be included in a `pyproject.toml` file, it is not allowed in this context.
          
          [env: UV_CONFIG_FILE=]

      --no-config
          Avoid discovering configuration files (`pyproject.toml`, `uv.toml`).
          
          Normally, configuration files are discovered in the current directory, parent directories, or user configuration directories.
          
          [env: UV_NO_CONFIG=]

  -h, --help
          Display the concise help for this command

  -V, --version
          Display the uv version
```
