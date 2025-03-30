sudo apt install openjdk-24-jdk

## Usage
```
Usage: jar [OPTION...] [ [--release VERSION] [-C dir] files] ...
jar creates an archive for classes and resources, and can manipulate or
restore individual classes or resources from an archive.

 Examples:
 # Create an archive called classes.jar with two class files:
 jar --create --file classes.jar Foo.class Bar.class
 # Create an archive using an existing manifest, with all the files in foo/:
 jar --create --file classes.jar --manifest mymanifest -C foo/ .
 # Create a modular jar archive, where the module descriptor is located in
 # classes/module-info.class:
 jar --create --file foo.jar --main-class com.foo.Main --module-version 1.0
     -C foo/ classes resources
 # Update an existing non-modular jar to a modular jar:
 jar --update --file foo.jar --main-class com.foo.Main --module-version 1.0
     -C foo/ module-info.class
 # Create a multi-release jar, placing some files in the META-INF/versions/9 directory:
 jar --create --file mr.jar -C foo classes --release 9 -C foo9 classes

To shorten or simplify the jar command, you can specify arguments in a separate
text file and pass it to the jar command with the at sign (@) as a prefix.

 Examples:
 # Read additional options and list of class files from the file classes.list
 jar --create --file my.jar @classes.list


 Main operation mode:

  -c, --create               Create the archive. When the archive file name specified
                             by -f or --file contains a path, missing parent directories
                             will also be created
  -i, --generate-index=FILE  Generate index information for the specified jar
                             archives. This option is deprecated and may be 
                             removed in a future release.
  -t, --list                 List the table of contents for the archive
  -u, --update               Update an existing jar archive
  -x, --extract              Extract named (or all) files from the archive.
                             If a file with the same name appears more than once in
                             the archive, each copy will be extracted, with later copies
                             overwriting (replacing) earlier copies unless -k is specified.
  -d, --describe-module      Print the module descriptor, or automatic module name
      --validate             Validate the contents of the jar archive. This option
                             will validate that the API exported by a multi-release
                             jar archive is consistent across all different release
                             versions.

 Operation modifiers valid in any mode:

  -C DIR                     Change to the specified directory and include the
                             following file. When used in extract mode, extracts
                             the jar to the specified directory
  -f, --file=FILE            The archive file name. When omitted, either stdin or
                             stdout is used based on the operation
      --release VERSION      Places all following files in a versioned directory
                             of the jar (i.e. META-INF/versions/VERSION/)
  -v, --verbose              Generate verbose output on standard output

 Operation modifiers valid only in create and update mode:

  -e, --main-class=CLASSNAME The application entry point for stand-alone
                             applications bundled into a modular, or executable,
                             jar archive
  -m, --manifest=FILE        Include the manifest information from the given
                             manifest file
  -M, --no-manifest          Do not create a manifest file for the entries
      --module-version=VERSION    The module version, when creating a modular
                             jar, or updating a non-modular jar
      --hash-modules=PATTERN Compute and record the hashes of modules 
                             matched by the given pattern and that depend upon
                             directly or indirectly on a modular jar being
                             created or a non-modular jar being updated
  -p, --module-path          Location of module dependence for generating
                             the hash

 Operation modifiers valid only in create, update, and generate-index mode:

  -0, --no-compress          Store only; use no ZIP compression
      --date=TIMESTAMP       The timestamp in ISO-8601 extended offset date-time with
                             optional time-zone format, to use for the timestamps of
                             entries, e.g. "2022-02-12T12:30:00-05:00"

 Operation modifiers valid only in extract mode:

  -k, --keep-old-files       Do not overwrite existing files.
                             If a Jar file entry with the same name exists in the target
                             directory, the existing file will not be overwritten.
                             As a result, if a file appears more than once in an
                             archive, later copies will not overwrite earlier copies.
                             Also note that some file system can be case insensitive.
  --dir                    Directory into which the jar will be extracted

 Other options:

  -?, -h, --help[:compat]    Give this, or optionally the compatibility, help
      --help-extra           Give help on extra options
      --version              Print program version

 An archive is a modular jar if a module descriptor, 'module-info.class', is
 located in the root of the given directories, or the root of the jar archive
 itself. The following operations are only valid when creating a modular jar,
 or updating an existing non-modular jar: '--module-version',
 '--hash-modules', and '--module-path'.

 Mandatory or optional arguments to long options are also mandatory or optional
 for any corresponding short options.
```
