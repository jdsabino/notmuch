.. program:: notmuch compact

.. option:: --backup=<directory>

    Save the current database to the given directory before
    replacing it with the compacted database. The backup directory
    must not exist and it must reside on the same mounted filesystem
    as the current database.

.. option:: --quiet
     
    Do not report database compaction progress to stdout.
