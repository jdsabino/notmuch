:file:`$DATABASEDIR/.notmuch/hooks/*`

Hooks are scripts (or arbitrary executables or symlinks to such) that
notmuch invokes before and after certain actions. These scripts reside
in the .notmuch/hooks directory within the database directory and must
have executable permissions.

The currently available hooks are described below.

:pre-new:
    This hook is invoked by the :ref:`notmuch-new` command before scanning or
    importing new messages into the database. If this hook exits
    with a non-zero status, notmuch will abort further processing of
    the :ref:`notmuch-new` command.

    Typically this hook is used for fetching or delivering new mail
    to be imported into the database.

:post-new:
    This hook is invoked by the :ref:`notmuch-new` command after new messages
    have been imported into the database and initial tags have been
    applied. The hook will not be run if there have been any errors
    during the scan or import.

    Typically this hook is used to perform additional query-based
    tagging on the imported messages.

:post-insert:
    This hook is invoked by the :ref:`notmuch-insert` command after the
    message has been delivered, added to the database, and initial
    tags have been applied. The hook will not be run if there have
    been any errors during the message delivery; what is regarded
    as succesful delivery depends on the :option:`--keep <notmuch insert --keep>` option.

    Typically this hook is used to perform additional query-based
    tagging on the delivered messages.
