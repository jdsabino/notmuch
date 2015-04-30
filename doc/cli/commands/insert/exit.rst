This command returns exit status 0 on succesful mail delivery,
non-zero otherwise. The default is to indicate failed mail delivery on
any errors, including message file delivery to the filesystem, message
indexing to Notmuch database, changing tags, and synchronizing tags to
maildir flags. The ``--keep`` option may be used to settle for
successful message file delivery.

The exit status of the **post-insert** hook does not affect the exit
status of the **insert** command.
