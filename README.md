Install by placing `rum` in `/usr/local/bin/` and making it executable.
Then place the `/usr/` contents of wine packages into directories in `/opt/wines`, e.g:

    $ ls /opt/wines/wine-staging-pba-3.7-1-x86_64/
    bin  include  lib  lib32  share

You can put your wine versions in another directory, but then you'll need to specify the full path to them instead or change the directory in rum itself.

Now you can run `rum wine-staging-pba-3.7-1-x86_64 ./wineprefix wine app.exe` where the first argument is the version of wine to use, the second is the prefix directory and the remaining are any commands you want which can be `wine` itself or `winecfg` and `winetricks` when setting up a prefix.
You can also run `rum` without any arguments to get usage information and a list of the wine versions you have available.

TODO:
* Search another directory for wine versions e.g: $XDG_DATA_HOME/wines
* Implement an overlayfs based system for wine prefixes that share the same version of wine to deduplicate files and speed up creation.
    