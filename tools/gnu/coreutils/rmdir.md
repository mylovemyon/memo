## Usage
```
Usage: rmdir [OPTION]... DIRECTORY...
Remove the DIRECTORY(ies), if they are empty.

      --ignore-fail-on-non-empty
                    ignore each failure to remove a non-empty directory
  -p, --parents     remove DIRECTORY and its ancestors;
                    e.g., 'rmdir -p a/b' is similar to 'rmdir a/b a'

  -v, --verbose     output a diagnostic for every directory processed
      --help        display this help and exit
      --version     output version information and exit

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/rmdir>
or available locally via: info '(coreutils) rmdir invocation'
```

## man 1
```
RMDIR(1)                                                                                                       User Commands                                                                                                       RMDIR(1)

NAME
       rmdir - remove empty directories

SYNOPSIS
       rmdir [OPTION]... DIRECTORY...

DESCRIPTION
       Remove the DIRECTORY(ies), if they are empty.

       --ignore-fail-on-non-empty
              ignore each failure to remove a non-empty directory

       -p, --parents
              remove DIRECTORY and its ancestors; e.g., 'rmdir -p a/b' is similar to 'rmdir a/b a'

       -v, --verbose
              output a diagnostic for every directory processed

       --help display this help and exit

       --version
              output version information and exit

AUTHOR
       Written by David MacKenzie.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report any translation bugs to <https://translationproject.org/team/>

COPYRIGHT
       Copyright © 2024 Free Software Foundation, Inc.  License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
       This is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the extent permitted by law.

SEE ALSO
       rmdir(2)

       Full documentation <https://www.gnu.org/software/coreutils/rmdir>
       or available locally via: info '(coreutils) rmdir invocation'

GNU coreutils 9.5                                                                                               October 2024                                                                                                       RMDIR(1)
```

## man 2
```
rmdir(2)                                                                                                    System Calls Manual                                                                                                    rmdir(2)

NAME
       rmdir - delete a directory

LIBRARY
       Standard C library (libc, -lc)

SYNOPSIS
       #include <unistd.h>

       int rmdir(const char *pathname);

DESCRIPTION
       rmdir() deletes a directory, which must be empty.

RETURN VALUE
       On success, zero is returned.  On error, -1 is returned, and errno is set to indicate the error.

ERRORS
       EACCES Write access to the directory containing pathname was not allowed, or one of the directories in the path prefix of pathname did not allow search permission.  (See also path_resolution(7).)

       EBUSY  pathname is currently in use by the system or some process that prevents its removal.  On Linux, this means pathname is currently used as a mount point or is the root directory of the calling process.

       EFAULT pathname points outside your accessible address space.

       EINVAL pathname has .  as last component.

       ELOOP  Too many symbolic links were encountered in resolving pathname.

       ENAMETOOLONG
              pathname was too long.

       ENOENT A directory component in pathname does not exist or is a dangling symbolic link.

       ENOMEM Insufficient kernel memory was available.

       ENOTDIR
              pathname, or a component used as a directory in pathname, is not, in fact, a directory.

       ENOTEMPTY
              pathname contains entries other than . and .. ; or, pathname has ..  as its final component.  POSIX.1 also allows EEXIST for this condition.

       EPERM  The directory containing pathname has the sticky bit (S_ISVTX) set and the process's effective user ID is neither the user ID of the file to be deleted nor that of the directory containing it, and the process is not priv‐
              ileged (Linux: does not have the CAP_FOWNER capability).

       EPERM  The filesystem containing pathname does not support the removal of directories.

       EROFS  pathname refers to a directory on a read-only filesystem.

STANDARDS
       POSIX.1-2008.

HISTORY
       POSIX.1-2001, SVr4, 4.3BSD.

BUGS
       Infelicities in the protocol underlying NFS can cause the unexpected disappearance of directories which are still being used.

SEE ALSO
       rm(1), rmdir(1), chdir(2), chmod(2), mkdir(2), rename(2), unlink(2), unlinkat(2)

Linux man-pages 6.9.1                                                                                            2024-05-02                                                                                                        rmdir(2)
```
