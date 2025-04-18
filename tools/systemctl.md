```
systemctl [OPTIONS...] COMMAND ...

Query or send control commands to the system manager.

Unit Commands:
  list-units [PATTERN...]             List units currently in memory
  list-automounts [PATTERN...]        List automount units currently in memory,
                                      ordered by path
  list-paths [PATTERN...]             List path units currently in memory,
                                      ordered by path
  list-sockets [PATTERN...]           List socket units currently in memory,
                                      ordered by address
  list-timers [PATTERN...]            List timer units currently in memory,
                                      ordered by next elapse
  is-active PATTERN...                Check whether units are active
  is-failed [PATTERN...]              Check whether units are failed or
                                      system is in degraded state
  status [PATTERN...|PID...]          Show runtime status of one or more units
  show [PATTERN...|JOB...]            Show properties of one or more
                                      units/jobs or the manager
  cat PATTERN...                      Show files and drop-ins of specified units
  help PATTERN...|PID...              Show manual for one or more units
  list-dependencies [UNIT...]         Recursively show units which are required
                                      or wanted by the units or by which those
                                      units are required or wanted
  start UNIT...                       Start (activate) one or more units
  stop UNIT...                        Stop (deactivate) one or more units
  reload UNIT...                      Reload one or more units
  restart UNIT...                     Start or restart one or more units
  try-restart UNIT...                 Restart one or more units if active
  reload-or-restart UNIT...           Reload one or more units if possible,
                                      otherwise start or restart
  try-reload-or-restart UNIT...       If active, reload one or more units,
                                      if supported, otherwise restart
  isolate UNIT                        Start one unit and stop all others
  kill UNIT...                        Send signal to processes of a unit
  clean UNIT...                       Clean runtime, cache, state, logs or
                                      configuration of unit
  freeze PATTERN...                   Freeze execution of unit processes
  thaw PATTERN...                     Resume execution of a frozen unit
  set-property UNIT PROPERTY=VALUE... Sets one or more properties of a unit
  bind UNIT PATH [PATH]               Bind-mount a path from the host into a
                                      unit's namespace
  mount-image UNIT PATH [PATH [OPTS]] Mount an image from the host into a
                                      unit's namespace
  service-log-level SERVICE [LEVEL]   Get/set logging threshold for service
  service-log-target SERVICE [TARGET] Get/set logging target for service
  reset-failed [PATTERN...]           Reset failed state for all, one, or more
                                      units
  whoami [PID...]                     Return unit caller or specified PIDs are
                                      part of

Unit File Commands:
  list-unit-files [PATTERN...]        List installed unit files
  enable [UNIT...|PATH...]            Enable one or more unit files
  disable UNIT...                     Disable one or more unit files
  reenable UNIT...                    Reenable one or more unit files
  preset UNIT...                      Enable/disable one or more unit files
                                      based on preset configuration
  preset-all                          Enable/disable all unit files based on
                                      preset configuration
  is-enabled UNIT...                  Check whether unit files are enabled
  mask UNIT...                        Mask one or more units
  unmask UNIT...                      Unmask one or more units
  link PATH...                        Link one or more units files into
                                      the search path
  revert UNIT...                      Revert one or more unit files to vendor
                                      version
  add-wants TARGET UNIT...            Add 'Wants' dependency for the target
                                      on specified one or more units
  add-requires TARGET UNIT...         Add 'Requires' dependency for the target
                                      on specified one or more units
  edit UNIT...                        Edit one or more unit files
  get-default                         Get the name of the default target
  set-default TARGET                  Set the default target

Machine Commands:
  list-machines [PATTERN...]          List local containers and host

Job Commands:
  list-jobs [PATTERN...]              List jobs
  cancel [JOB...]                     Cancel all, one, or more jobs

Environment Commands:
  show-environment                    Dump environment
  set-environment VARIABLE=VALUE...   Set one or more environment variables
  unset-environment VARIABLE...       Unset one or more environment variables
  import-environment VARIABLE...      Import all or some environment variables

Manager State Commands:
  daemon-reload                       Reload systemd manager configuration
  daemon-reexec                       Reexecute systemd manager
  log-level [LEVEL]                   Get/set logging threshold for manager
  log-target [TARGET]                 Get/set logging target for manager
  service-watchdogs [BOOL]            Get/set service watchdog state

System Commands:
  is-system-running                   Check whether system is fully running
  default                             Enter system default mode
  rescue                              Enter system rescue mode
  emergency                           Enter system emergency mode
  halt                                Shut down and halt the system
  poweroff                            Shut down and power-off the system
  reboot                              Shut down and reboot the system
  kexec                               Shut down and reboot the system with kexec
  soft-reboot                         Shut down and reboot userspace
  exit [EXIT_CODE]                    Request user instance or container exit
  switch-root [ROOT [INIT]]           Change to a different root file system
  sleep                               Put the system to sleep (through one of
                                      the operations below)
  suspend                             Suspend the system
  hibernate                           Hibernate the system
  hybrid-sleep                        Hibernate and suspend the system
  suspend-then-hibernate              Suspend the system, wake after a period of
                                      time, and hibernate
Options:
  -h --help              Show this help
     --version           Show package version
     --system            Connect to system manager
     --user              Connect to user service manager
  -C --capsule=NAME      Connect to service manager of specified capsule
  -H --host=[USER@]HOST  Operate on remote host
  -M --machine=CONTAINER Operate on a local container
  -t --type=TYPE         List units of a particular type
     --state=STATE       List units with particular LOAD or SUB or ACTIVE state
     --failed            Shortcut for --state=failed
  -p --property=NAME     Show only properties by this name
  -P NAME                Equivalent to --value --property=NAME
  -a --all               Show all properties/all units currently in memory,
                         including dead/empty ones. To list all units installed
                         on the system, use 'list-unit-files' instead.
  -l --full              Don't ellipsize unit names on output
  -r --recursive         Show unit list of host and local containers
     --reverse           Show reverse dependencies with 'list-dependencies'
     --before            Show units ordered before with 'list-dependencies'
     --after             Show units ordered after with 'list-dependencies'
     --with-dependencies Show unit dependencies with 'status', 'cat',
                         'list-units', and 'list-unit-files'.
     --job-mode=MODE     Specify how to deal with already queued jobs, when
                         queueing a new job
  -T --show-transaction  When enqueuing a unit job, show full transaction
     --show-types        When showing sockets, explicitly show their type
     --value             When showing properties, only print the value
     --check-inhibitors=MODE
                         Whether to check inhibitors before shutting down,
                         sleeping, or hibernating
  -i                     Shortcut for --check-inhibitors=no
     --kill-whom=WHOM    Whom to send signal to
     --kill-value=INT    Signal value to enqueue
  -s --signal=SIGNAL     Which signal to send
     --what=RESOURCES    Which types of resources to remove
     --now               Start or stop unit after enabling or disabling it
     --dry-run           Only print what would be done
                         Currently supported by verbs: halt, poweroff, reboot,
                             kexec, soft-reboot, suspend, hibernate, 
                             suspend-then-hibernate, hybrid-sleep, default,
                             rescue, emergency, and exit.
  -q --quiet             Suppress output
     --no-warn           Suppress several warnings shown by default
     --wait              For (re)start, wait until service stopped again
                         For is-system-running, wait until startup is completed
                         For kill, wait until service stopped
     --no-block          Do not wait until operation finished
     --no-wall           Don't send wall message before halt/power-off/reboot
     --message=MESSAGE   Specify human readable reason for system shutdown
     --no-reload         Don't reload daemon after en-/dis-abling unit files
     --legend=BOOL       Enable/disable the legend (column headers and hints)
     --no-pager          Do not pipe output into a pager
     --no-ask-password   Do not ask for system passwords
     --global            Edit/enable/disable/mask default user unit files
                         globally
     --runtime           Edit/enable/disable/mask unit files temporarily until
                         next reboot
  -f --force             When enabling unit files, override existing symlinks
                         When shutting down, execute action immediately
     --preset-mode=      Apply only enable, only disable, or all presets
     --root=PATH         Edit/enable/disable/mask unit files in the specified
                         root directory
     --image=PATH        Edit/enable/disable/mask unit files in the specified
                         disk image
     --image-policy=POLICY
                         Specify disk image dissection policy
  -n --lines=INTEGER     Number of journal entries to show
  -o --output=STRING     Change journal output mode (short, short-precise,
                             short-iso, short-iso-precise, short-full,
                             short-monotonic, short-unix, short-delta,
                             verbose, export, json, json-pretty, json-sse, cat)
     --firmware-setup    Tell the firmware to show the setup menu on next boot
     --boot-loader-menu=TIME
                         Boot into boot loader menu on next boot
     --boot-loader-entry=NAME
                         Boot into a specific boot loader entry on next boot
     --reboot-argument=ARG
                         Specify argument string to pass to reboot()
     --plain             Print unit dependencies as a list instead of a tree
     --timestamp=FORMAT  Change format of printed timestamps (pretty, unix,
                             us, utc, us+utc)
     --read-only         Create read-only bind mount
     --mkdir             Create directory before mounting, if missing
     --marked            Restart/reload previously marked units
     --drop-in=NAME      Edit unit files using the specified drop-in file name
     --when=TIME         Schedule halt/power-off/reboot/kexec action after
                         a certain timestamp
     --stdin             Read new contents of edited file from stdin

See the systemctl(1) man page for details.
```
