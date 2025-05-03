## Options
```
printf: printf [-v var] format [arguments]
    Formats and prints ARGUMENTS under control of the FORMAT.
    
    Options:
      -v var    assign the output to shell variable VAR rather than
                display it on the standard output
    
    FORMAT is a character string which contains three types of objects: plain
    characters, which are simply copied to standard output; character escape
    sequences, which are converted and copied to the standard output; and
    format specifications, each of which causes printing of the next successive
    argument.
    
    In addition to the standard format specifications described in printf(1),
    printf interprets:
    
      %b        expand backslash escape sequences in the corresponding argument
      %q        quote the argument in a way that can be reused as shell input
      %Q        like %q, but apply any precision to the unquoted argument before
                quoting
      %(fmt)T   output the date-time string resulting from using FMT as a format
                string for strftime(3)
    
    The format is re-used as necessary to consume all of the arguments.  If
    there are fewer arguments than the format requires,  extra format
    specifications behave as if a zero value or null string, as appropriate,
    had been supplied.
    
    Exit Status:
    Returns success unless an invalid option is given or a write or assignment
    error occurs.
```

## man
```
PRINTF(1)                                                                                                      User Commands                                                                                                      PRINTF(1)

NAME
       printf - format and print data

SYNOPSIS
       printf FORMAT [ARGUMENT]...
       printf OPTION

DESCRIPTION
       Print ARGUMENT(s) according to FORMAT, or execute according to OPTION:

       --help display this help and exit

       --version
              output version information and exit

       FORMAT controls the output as in C printf.  Interpreted sequences are:

       \"     double quote

       \\     backslash

       \a     alert (BEL)

       \b     backspace

       \c     produce no further output

       \e     escape

       \f     form feed

       \n     new line

       \r     carriage return

       \t     horizontal tab

       \v     vertical tab

       \NNN   byte with octal value NNN (1 to 3 digits)

       \xHH   byte with hexadecimal value HH (1 to 2 digits)

       \uHHHH Unicode (ISO/IEC 10646) character with hex value HHHH (4 digits)

       \UHHHHHHHH
              Unicode character with hex value HHHHHHHH (8 digits)

       %%     a single %

       %b     ARGUMENT as a string with '\' escapes interpreted, except that octal escapes are of the form \0 or \0NNN

       %q     ARGUMENT is printed in a format that can be reused as shell input, escaping non-printable characters with the proposed POSIX $'' syntax.

       and all C format specifications ending with one of diouxXfeEgGcs, with ARGUMENTs converted to proper type first.  Variable widths are handled.

       Your shell may have its own version of printf, which usually supersedes the version described here.  Please refer to your shell's documentation for details about the options it supports.

AUTHOR
       Written by David MacKenzie.

REPORTING BUGS
       GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
       Report any translation bugs to <https://translationproject.org/team/>

COPYRIGHT
       Copyright © 2024 Free Software Foundation, Inc.  License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
       This is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the extent permitted by law.

SEE ALSO
       printf(3)

       Full documentation <https://www.gnu.org/software/coreutils/printf>
       or available locally via: info '(coreutils) printf invocation'

GNU coreutils 9.5                                                                                               October 2024                                                                                                      PRINTF(1)
```
