## egrep
```
#!/bin/sh
cmd=${0##*/}
exec grep -E "$@"
```

## fgrep
```
#!/bin/sh
cmd=${0##*/}
exec grep -F "$@"
```

## rgrep
```
#!/bin/sh

exec grep -r "$@"
```
