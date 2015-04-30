**notmuch insert** reads a message from standard input and delivers it
into the maildir directory given by configuration option
**database.path**, then incorporates the message into the notmuch
database. It is an alternative to using a separate tool to deliver the
message then running **notmuch new** afterwards.

The new message will be tagged with the tags specified by the
**new.tags** configuration option, then by operations specified on the
command-line: tags prefixed by '+' are added while those prefixed by '-'
are removed.

If the new message is a duplicate of an existing message in the database
(it has same Message-ID), it will be added to the maildir folder and
notmuch database, but the tags will not be changed.

The **insert** command supports hooks. See **notmuch-hooks(5)** for
more details on hooks.
