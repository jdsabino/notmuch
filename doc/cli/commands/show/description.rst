The messages will be grouped and sorted based on the threading (all
replies to a particular message will appear immediately after that
message in date order). The output is not indented by default, but depth
tags are printed so that proper indentation can be performed by a
post-processor (such as the emacs interface to notmuch).

See :ref:`search-terms` for details of the supported syntax for `<search-terms>`.

A common use of :command:`notmuch show` is to display a single thread of email
messages. For this, use a search term of "thread:<thread-id>" as can be
seen in the first column of output from the :command:`notmuch search` command.

