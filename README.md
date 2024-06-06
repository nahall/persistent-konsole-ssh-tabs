# persistent-konsole-ssh-tabs
Easily resume multiple SSH connections in Konsole tabs

This is designed to open a "konsole" terminal window containing multiple tabs that each connect
to a server over SSH. Each tab connects to a different shell that is running "dtach" on the
remote server so that the terminal window can be closed but then later easily resumed, with
the status of all the tabs intact.

I wanted to do it this way rather than using something like mosh or tmux because all then the
scrollback buffer works on the local konsole window. It essentially feels exactly the same as a
normal SSH session.

To open the konsole window, run:
konsole --tabs-from-file /home/myuser/persistent-konsole-ssh-tabs/konsole-tabs
