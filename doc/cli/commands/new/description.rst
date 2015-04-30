The `new` command scans all sub-directories of the database,
performing full-text indexing on new messages that are found. Each new
message will automatically be tagged with both the `inbox` and
`unread` tags.

You should run :command:`notmuch new` once after first running 
:command:`notmuch setup` to create the initial database. The first run may take a long
time if you have a significant amount of mail (several hundred thousand
messages or more). Subsequently, you should run :command:`notmuch new` whenever
new mail is delivered and you wish to incorporate it into the database.
These subsequent runs will be much quicker than the initial run.

Invoking :command:`notmuch` with no command argument will run :command:`new` if
:command:`notmuch setup` has previously been completed, but :command:`notmuch new` has
not previously been run.

:command:`notmuch new` updates tags according to maildir flag changes if the
:term:`maildir.synchronize_flags` configuration option is enabled. See
:ref:`config` for details.

The `new` command supports hooks. See :ref:`hooks` for more details on hooks.
