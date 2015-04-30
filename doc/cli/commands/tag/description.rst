Tags prefixed by '+' are added while those prefixed by '-' are removed.
For each message, tag changes are applied in the order they appear on
the command line.

The beginning of the search terms is recognized by the first argument
that begins with neither '+' nor '-'. Support for an initial search term
beginning with '+' or '-' is provided by allowing the user to specify a
"--" argument to separate the tags from the search terms.

**notmuch tag** updates the maildir flags according to tag changes if
the :term:`maildir.synchronize_flags` configuration option is enabled.
See **notmuch-config(1)** for details.
