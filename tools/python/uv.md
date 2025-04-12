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
