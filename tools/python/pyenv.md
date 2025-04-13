https://github.com/pyenv/pyenv
## Usage
```
Usage: pyenv <command> [<args>]

Some useful pyenv commands are:
   activate    Activate virtual environment
   commands    List all available pyenv commands
   deactivate   Deactivate virtual environment
   doctor      Verify pyenv installation and development tools to build pythons.
   exec        Run an executable with the selected Python version
   global      Set or show the global Python version(s)
   help        Display help for a command
   hooks       List hook scripts for a given pyenv command
   init        Configure the shell environment for pyenv
   install     Install a Python version using python-build
   latest      Print the latest installed or known version with the given prefix
   local       Set or show the local application-specific Python version(s)
   prefix      Display prefixes for Python versions
   rehash      Rehash pyenv shims (run this after installing executables)
   root        Display the root directory where versions and shims are kept
   shell       Set or show the shell-specific Python version
   shims       List existing pyenv shims
   uninstall   Uninstall Python versions
   update      Update pyenv, its plugins including the list of available versions
   --version   Display the version of pyenv
   version     Show the current Python version(s) and its origin
   version-file   Detect the file that sets the current pyenv version
   version-name   Show the current Python version
   version-origin   Explain how the current Python version is set
   versions    List all Python versions available to pyenv
   virtualenv   Create a Python virtualenv using the pyenv-virtualenv plugin
   virtualenv-delete   Uninstall a specific Python virtualenv
   virtualenv-init   Configure the shell environment for pyenv-virtualenv
   virtualenv-prefix   Display real_prefix for a Python virtualenv version
   virtualenvs   List all Python virtualenvs found in `$PYENV_ROOT/versions/*'.
   whence      List all Python versions that contain the given executable
   which       Display the full path to an executable

See `pyenv help <command>' for information on a specific command.
For full documentation, see: https://github.com/pyenv/pyenv#readme
```


## install
```
Usage: pyenv install [-f] [-kvp] <version>...
       pyenv install [-f] [-kvp] <definition-file>
       pyenv install -l|--list
       pyenv install --version

  -l/--list          List all available versions
  -f/--force         Install even if the version appears to be installed already
  -s/--skip-existing Skip if the version appears to be installed already

  python-build options:

  -k/--keep          Keep source tree in $PYENV_BUILD_ROOT after installation
                     (defaults to $PYENV_ROOT/sources)
  -p/--patch         Apply a patch from stdin before building
  -v/--verbose       Verbose mode: print compilation status to stdout
  --version          Show version of python-build
  -g/--debug         Build a debug version

For detailed information on installing Python versions with
python-build, including a list of environment variables for adjusting
compilation, see: https://github.com/pyenv/pyenv#readme
```


## local
```
└─$ pyenv help local
Usage: pyenv local [-f|--force] [<version> [...]]
       pyenv local --unset

  -f/--force    Do not verify that the versions being set exist

Sets the local application-specific Python version(s) by writing the
version name to a file named `.python-version'.

When you run a Python command, pyenv will look for a `.python-version'
file in the current directory and each parent directory. If no such
file is found in the tree, pyenv will use the global Python version
specified with `pyenv global'. A version specified with the
`PYENV_VERSION' environment variable takes precedence over local
and global versions.

<version> can be specified multiple times and should be a version
tag known to pyenv.  The special version string `system' will use
your default system Python.  Run `pyenv versions' for a list of
available Python versions.

Example: To enable the python2.7 and python3.7 shims to find their
         respective executables you could set both versions with:

'pyenv local 3.7.0 2.7.15'
```


## shell
```
Usage: pyenv shell <version>...
       pyenv shell -
       pyenv shell --unset

Sets a shell-specific Python version by setting the `PYENV_VERSION'
environment variable in your shell. This version overrides local
application-specific versions and the global version.

<version> should be a string matching a Python version known to pyenv.
The special version string `system' will use your default system Python.
Run `pyenv versions' for a list of available Python versions.

When `-` is passed instead of the version string, the previously set
version will be restored. With `--unset`, the `PYENV_VERSION`
environment variable gets unset, restoring the environment to the
state before the first `pyenv shell` call.
```
