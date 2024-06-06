# persistent-konsole-ssh-tabs
Easily resume multiple SSH connections in Konsole tabs

This is designed to open a "konsole" terminal window containing multiple tabs that each connect
to a server over SSH. Each tab connects to a different shell that is running "dtach" on the
remote server so that the terminal window can be closed but then later easily resumed, with
the status of all the tabs intact.

I wanted to do it this way rather than using something like mosh or tmux because all then the
scrollback buffer works on the local konsole window. It essentially feels exactly the same as a
normal SSH session but you can reboot your client computer and then resume everything instantly.

This repository is just an example of how to do this. You'll need to edit the files to
accomplish what you want it to do. My examples shows how to open 8 konsole tabs.

You'll need to edit each tab file "konsole-tab-1", etc, to set your SSH server and server.
This works best if you are using SSH keys. You also may want to edit the filename that is
passed to dtach -A as that is how each tab is made persistent. It can be anything, but
each tab needs to have a unique filename.

Then edit the file "konsole-tabs". You can set the title that appears in Konsole for each
tab and also the Konsole profile used for each one. You'll need one line for each tab
that you want to open.

To open the konsole window containing all the tabs, run:
konsole --tabs-from-file /home/myuser/persistent-konsole-ssh-tabs/konsole-tabs
