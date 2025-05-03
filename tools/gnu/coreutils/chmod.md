## Usage
```
Usage: chmod [OPTION]... MODE[,MODE]... FILE...
  or:  chmod [OPTION]... OCTAL-MODE FILE...
  or:  chmod [OPTION]... --reference=RFILE FILE...
Change the mode of each FILE to MODE.
With --reference, change the mode of each FILE to that of RFILE.

  -c, --changes          like verbose but report only when a change is made
  -f, --silent, --quiet  suppress most error messages
  -v, --verbose          output a diagnostic for every file processed
      --dereference      affect the referent of each symbolic link,
                           rather than the symbolic link itself
  -h, --no-dereference   affect each symbolic link, rather than the referent
      --no-preserve-root  do not treat '/' specially (the default)
      --preserve-root    fail to operate recursively on '/'
      --reference=RFILE  use RFILE's mode instead of specifying MODE values.
                         RFILE is always dereferenced if a symbolic link.
  -R, --recursive        change files and directories recursively

The following options modify how a hierarchy is traversed when the -R
option is also specified.  If more than one is specified, only the final
one takes effect. '-H' is the default.

  -H                     if a command line argument is a symbolic link
                         to a directory, traverse it
  -L                     traverse every symbolic link to a directory
                         encountered
  -P                     do not traverse any symbolic links

      --help        display this help and exit
      --version     output version information and exit

Each MODE is of the form '[ugoa]*([-+=]([rwxXst]*|[ugo]))+|[-+=][0-7]+'.

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Full documentation <https://www.gnu.org/software/coreutils/chmod>
or available locally via: info '(coreutils) chmod invocation'
```

## man 1
```
CHMOD(1)                                                                                                       User Commands                                                                                                       CHMOD(1)

NAME
       chmod - change file mode bits

SYNOPSIS
       chmod [OPTION]... MODE[,MODE]... FILE...
       chmod [OPTION]... OCTAL-MODE FILE...
       chmod [OPTION]... --reference=RFILE FILE...

DESCRIPTION
       This  manual  page documents the GNU version of chmod.  chmod changes the file mode bits of each given file according to mode, which can be either a symbolic representation of changes to make, or an octal number representing the
       bit pattern for the new mode bits.

       The format of a symbolic mode is [ugoa...][[-+=][perms...]...], where perms is either zero or more letters from the set rwxXst, or a single letter from the set ugo.  Multiple symbolic modes can be given, separated by commas.

       A combination of the letters ugoa controls which users' access to the file will be changed: the user who owns it (u), other users in the file's group (g), other users not in the file's group (o), or all users (a).   If  none  of
       these are given, the effect is as if (a) were given, but bits that are set in the umask are not affected.

       The operator + causes the selected file mode bits to be added to the existing file mode bits of each file; - causes them to be removed; and = causes them to be added and causes unmentioned bits to be removed except that a direc‐
       tory's unmentioned set user and group ID bits are not affected.

       The  letters  rwxXst select file mode bits for the affected users: read (r), write (w), execute (or search for directories) (x), execute/search only if the file is a directory or already has execute permission for some user (X),
       set user or group ID on execution (s), restricted deletion flag or sticky bit (t).  Instead of one or more of these letters, you can specify exactly one of the letters ugo: the permissions granted to the user who owns  the  file
       (u), the permissions granted to other users who are members of the file's group (g), and the permissions granted to users that are in neither of the two preceding categories (o).

       A numeric mode is from one to four octal digits (0-7), derived by adding up the bits with values 4, 2, and 1.  Omitted digits are assumed to be leading zeros.  The first digit selects the set user ID (4) and set group ID (2) and
       restricted  deletion  or  sticky (1) attributes.  The second digit selects permissions for the user who owns the file: read (4), write (2), and execute (1); the third selects permissions for other users in the file's group, with
       the same values; and the fourth for other users not in the file's group, with the same values.

       chmod doesn't change the permissions of symbolic links; the chmod system call cannot change their permissions on most systems, and most systems ignore permissions of symbolic links.  However, for each symbolic link listed on the
       command line, chmod changes the permissions of the pointed-to file.  In contrast, chmod ignores symbolic links encountered during recursive directory traversals. Options that modify this behavior are  described  in  the  OPTIONS
       section.

SETUID AND SETGID BITS
       chmod  clears  the  set-group-ID bit of a regular file if the file's group ID does not match the user's effective group ID or one of the user's supplementary group IDs, unless the user has appropriate privileges.  Additional re‐
       strictions may cause the set-user-ID and set-group-ID bits of MODE or RFILE to be ignored.  This behavior depends on the policy and functionality of the underlying chmod system call.  When in doubt, check the  underlying  system
       behavior.

       For  directories chmod preserves set-user-ID and set-group-ID bits unless you explicitly specify otherwise.  You can set or clear the bits with symbolic modes like u+s and g-s.  To clear these bits for directories with a numeric
       mode requires an additional leading zero like 00755, leading minus like -6000, or leading equals like =755.

RESTRICTED DELETION FLAG OR STICKY BIT
       The restricted deletion flag or sticky bit is a single bit, whose interpretation depends on the file type.  For directories, it prevents unprivileged users from removing or renaming a file in the directory unless  they  own  the
       file  or the directory; this is called the restricted deletion flag for the directory, and is commonly found on world-writable directories like /tmp.  For regular files on some older systems, the bit saves the program's text im‐
       age on the swap device so it will load more quickly when run; this is called the sticky bit.

OPTIONS
       Change the mode of each FILE to MODE.  With --reference, change the mode of each FILE to that of RFILE.

       -c, --changes
              like verbose but report only when a change is made

       -f, --silent, --quiet
              suppress most error messages

       -v, --verbose
              output a diagnostic for every file processed

       --dereference
              affect the referent of each symbolic link, rather than the symbolic link itself

       -h, --no-dereference
              affect each symbolic link, rather than the referent

       --no-preserve-root
              do not treat '/' specially (the default)

       --preserve-root
              fail to operate recursively on '/'

       --reference=RFILE
              use RFILE's mode instead of specifying MODE values.  RFILE is always dereferenced if a symbolic link.

       -R, --recursive
              change files and directories recursively

       The following options modify how a hierarchy is traversed when the -R option is also specified.  If more than one is specified, only the final one takes effect. '-H' is the default.

       -H     if a command line argument is a symbolic link to a directory, traverse it

       -L     traverse every symbolic link to a directory encountered

       -P     do not traverse any symbolic links

       --help display this help and exit

       --version
              output version information and exit

       Each MODE is of the form '[ugoa]*([-+=]([rwxXst]*|[ugo]))+|[-+=][0-7]+'.

AUTHOR
       Written by David MacKenzie and Jim Meyering.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report any translation bugs to <https://translationproject.org/team/>

COPYRIGHT
       Copyright © 2024 Free Software Foundation, Inc.  License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
       This is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the extent permitted by law.

SEE ALSO
       chmod(2)

       Full documentation <https://www.gnu.org/software/coreutils/chmod>
       or available locally via: info '(coreutils) chmod invocation'

GNU coreutils 9.5                                                                                               October 2024                                                                                                       CHMOD(1)
```

## man 2
```
chmod(2)                                                                                                    System Calls Manual                                                                                                    chmod(2)

NAME
       chmod, fchmod, fchmodat - change permissions of a file

LIBRARY
       Standard C library (libc, -lc)

SYNOPSIS
       #include <sys/stat.h>

       int chmod(const char *pathname, mode_t mode);
       int fchmod(int fd, mode_t mode);

       #include <fcntl.h>           /* Definition of AT_* constants */
       #include <sys/stat.h>

       int fchmodat(int dirfd, const char *pathname, mode_t mode, int flags);

   Feature Test Macro Requirements for glibc (see feature_test_macros(7)):

       fchmod():
           Since glibc 2.24:
               _POSIX_C_SOURCE >= 199309L
           glibc 2.19 to glibc 2.23
               _POSIX_C_SOURCE
           glibc 2.16 to glibc 2.19:
               _BSD_SOURCE || _POSIX_C_SOURCE
           glibc 2.12 to glibc 2.16:
               _BSD_SOURCE || _XOPEN_SOURCE >= 500
                   || _POSIX_C_SOURCE >= 200809L
           glibc 2.11 and earlier:
               _BSD_SOURCE || _XOPEN_SOURCE >= 500

       fchmodat():
           Since glibc 2.10:
               _POSIX_C_SOURCE >= 200809L
           Before glibc 2.10:
               _ATFILE_SOURCE

DESCRIPTION
       The chmod() and fchmod() system calls change a file's mode bits.  (The file mode consists of the file permission bits plus the set-user-ID, set-group-ID, and sticky bits.)  These system calls differ only in how the file is spec‐
       ified:

       •  chmod() changes the mode of the file specified whose pathname is given in pathname, which is dereferenced if it is a symbolic link.

       •  fchmod() changes the mode of the file referred to by the open file descriptor fd.

       The new file mode is specified in mode, which is a bit mask created by ORing together zero or more of the following:

       S_ISUID  (04000)  set-user-ID (set process effective user ID on execve(2))

       S_ISGID  (02000)  set-group-ID (set process effective group ID on execve(2); mandatory locking, as described in fcntl(2); take a new file's group from parent directory, as described in chown(2) and mkdir(2))

       S_ISVTX  (01000)  sticky bit (restricted deletion flag, as described in unlink(2))

       S_IRUSR  (00400)  read by owner

       S_IWUSR  (00200)  write by owner

       S_IXUSR  (00100)  execute/search by owner ("search" applies for directories, and means that entries within the directory can be accessed)

       S_IRGRP  (00040)  read by group

       S_IWGRP  (00020)  write by group

       S_IXGRP  (00010)  execute/search by group

       S_IROTH  (00004)  read by others

       S_IWOTH  (00002)  write by others

       S_IXOTH  (00001)  execute/search by others

       The effective UID of the calling process must match the owner of the file, or the process must be privileged (Linux: it must have the CAP_FOWNER capability).

       If  the  calling  process  is not privileged (Linux: does not have the CAP_FSETID capability), and the group of the file does not match the effective group ID of the process or one of its supplementary group IDs, the S_ISGID bit
       will be turned off, but this will not cause an error to be returned.

       As a security measure, depending on the filesystem, the set-user-ID and set-group-ID execution bits may be turned off if a file is written.  (On Linux, this occurs if the writing process does not have the CAP_FSETID capability.)
       On some filesystems, only the superuser can set the sticky bit, which may have a special meaning.  For the sticky bit, and for set-user-ID and set-group-ID bits on directories, see inode(7).

       On NFS filesystems, restricting the permissions will immediately influence already open files, because the access control is done on the server, but open files are maintained by the client.  Widening the permissions may  be  de‐
       layed for other clients if attribute caching is enabled on them.

   fchmodat()
       The fchmodat() system call operates in exactly the same way as chmod(), except for the differences described here.

       If  the  pathname given in pathname is relative, then it is interpreted relative to the directory referred to by the file descriptor dirfd (rather than relative to the current working directory of the calling process, as is done
       by chmod() for a relative pathname).

       If pathname is relative and dirfd is the special value AT_FDCWD, then pathname is interpreted relative to the current working directory of the calling process (like chmod()).

       If pathname is absolute, then dirfd is ignored.

       flags can either be 0, or include the following flag:

       AT_SYMLINK_NOFOLLOW
              If pathname is a symbolic link, do not dereference it: instead operate on the link itself.  This flag is not currently implemented.

       See openat(2) for an explanation of the need for fchmodat().

RETURN VALUE
       On success, zero is returned.  On error, -1 is returned, and errno is set to indicate the error.

ERRORS
       Depending on the filesystem, errors other than those listed below can be returned.

       The more general errors for chmod() are listed below:

       EACCES Search permission is denied on a component of the path prefix.  (See also path_resolution(7).)

       EBADF  (fchmod()) The file descriptor fd is not valid.

       EBADF  (fchmodat()) pathname is relative but dirfd is neither AT_FDCWD nor a valid file descriptor.

       EFAULT pathname points outside your accessible address space.

       EINVAL (fchmodat()) Invalid flag specified in flags.

       EIO    An I/O error occurred.

       ELOOP  Too many symbolic links were encountered in resolving pathname.

       ENAMETOOLONG
              pathname is too long.

       ENOENT The file does not exist.

       ENOMEM Insufficient kernel memory was available.

       ENOTDIR
              A component of the path prefix is not a directory.

       ENOTDIR
              (fchmodat()) pathname is relative and dirfd is a file descriptor referring to a file other than a directory.

       ENOTSUP
              (fchmodat()) flags specified AT_SYMLINK_NOFOLLOW, which is not supported.

       EPERM  The effective UID does not match the owner of the file, and the process is not privileged (Linux: it does not have the CAP_FOWNER capability).

       EPERM  The file is marked immutable or append-only.  (See FS_IOC_SETFLAGS(2const).)

       EROFS  The named file resides on a read-only filesystem.

VERSIONS
   C library/kernel differences
       The GNU C library fchmodat() wrapper function implements the POSIX-specified interface described in this page.  This interface differs from the underlying Linux system call, which does not have a flags argument.

   glibc notes
       On older kernels where fchmodat() is unavailable, the glibc wrapper function falls back to the use of chmod().  When pathname is a relative pathname, glibc constructs a pathname based on the symbolic link in  /proc/self/fd  that
       corresponds to the dirfd argument.

STANDARDS
       POSIX.1-2008.

HISTORY
       chmod()
       fchmod()
              4.4BSD, SVr4, POSIX.1-2001.

       fchmodat()
              POSIX.1-2008.  Linux 2.6.16, glibc 2.4.

SEE ALSO
       chmod(1), chown(2), execve(2), open(2), stat(2), inode(7), path_resolution(7), symlink(7)

Linux man-pages 6.9.1                                                                                            2024-06-13                                                                                                        chmod(2)
```
