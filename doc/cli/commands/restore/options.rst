.. program:: notmuch restore

.. option:: --accumulate

        The union of the existing and new tags is applied, instead of
        replacing each message's tags as they are read in from the dump
        file.

.. option:: --format=(sup|batch-tag|auto)

        Notmuch restore supports two plain text dump formats, with each
        line specifying a message-id and a set of tags. For details of
        the actual formats, see :ref:`notmuch-dump`.

        **sup**
            The **sup** dump file format is specifically chosen to be
            compatible with the format of files produced by sup-dump. So
            if you've previously been using sup for mail, then the
            **notmuch restore** command provides you a way to import all
            of your tags (or labels as sup calls them).

        **batch-tag**
            The **batch-tag** dump format is intended to more robust
            against malformed message-ids and tags containing whitespace
            or non-:manpage:`ascii(7)` characters. See :command:`notmuch-dump`
            for details on this format.

            **notmuch restore** updates the maildir flags according to
            tag changes if the :term:`maildir.synchronize_flags`
            configuration option is enabled. See :ref:`notmuch-config`
            for details.

        **auto**
            This option (the default) tries to guess the format from the
            input. For correctly formed input in either supported
            format, this heuristic, based the fact that batch-tag format
            contains no parentheses, should be accurate.

.. option:: --input=<filename>

        Read input from given file instead of stdin.
