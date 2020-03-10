
# Tidy Backup Script by Jayro Alvarez

* -n Dry run; A dry run is where the script prints out what it would do, including all the files it would backup, where the files will go, the name of the tar archive, yet does not do any operations that would modify the file system.
* -r Remote backup; The destination is specified as an SSH style path. The path is specified as `user@remotehost:/fully/qualified/path`. The backup archive shall be sent over the network and stored on the remote host.
* -c N the number of backups to retain; this argument takes an option, N, which is the number of backups to retain.
* -v Verbose mode; Make the script very verbose by printing out every step that it does and every file that is being backed up.
* -h Help; print out a usage message

Note that the options are not mutually exclusive which means that any of the above options can be used in any combination with one another. Command line arguments can easily be processed using the getopts command.

In order to complete a remote backup, you will need to use the ssh command and the dd command or split command. If the output of the backup shall be small enough to fit in a single file, dd is a good utility to use. If the backup files will be too large, then use split to create many smaller files which can be reassembled to restore the computer.

Additionally, if the program is run without any parameters it prints out a usage message indicating the correct usage of the script. The usage message is like an online help message explaining to the user how to correctly invoke the script.
