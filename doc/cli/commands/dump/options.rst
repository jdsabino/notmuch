.. program:: notmuch dump

.. option::  --gzip

    Compress the output in a format compatible with **gzip(1)**.

.. option::  --format=(sup|batch-tag)

    Notmuch restore supports two plain text dump formats, both with one
    message-id per line, followed by a list of tags.

    **batch-tag**

        The default **batch-tag** dump format is intended to more
        robust against malformed message-ids and tags containing
        whitespace or non-\ **ascii(7)** characters. Each line has
        the form

            +<*encoded-tag*\ > +<*encoded-tag*\ > ... --
            id:<*quoted-message-id*\ >

        Tags are hex-encoded by replacing every byte not matching
        the regex **[A-Za-z0-9@=.,\_+-]** with **%nn** where nn is
        the two digit hex encoding. The message ID is a valid
        Xapian query, quoted using Xapian boolean term quoting
        rules: if the ID contains whitespace or a close paren or
        starts with a double quote, it must be enclosed in double
        quotes and double quotes inside the ID must be
        doubled. The astute reader will notice this is a special
        case of the batch input format for **notmuch-tag(1)**;
        note that the single message-id query is mandatory for
        **notmuch-restore(1)**.

    **sup**

        The **sup** dump file format is specifically chosen to be
        compatible with the format of files produced by
        sup-dump. So if you've previously been using sup for mail,
        then the **notmuch restore** command provides you a way to
        import all of your tags (or labels as sup calls
        them). Each line has the following form

            <*message-id*\ > **(** <*tag*\ > ... **)**

        with zero or more tags are separated by spaces. Note that
        (malformed) message-ids may contain arbitrary non-null
        characters. Note also that tags with spaces will not be
        correctly restored with this format.

.. option::  --output=<filename>

    Write output to given file instead of stdout.
