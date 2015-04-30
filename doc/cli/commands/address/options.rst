.. program:: notmuch address

.. option:: --format=(json||text|text0)

    Presents the results in either JSON, S-Expressions, newline
    character separated plain-text (default), or null character
    separated plain-text (compatible with **xargs(1)** -0 option
    where available).

.. option:: --format-version=N

    Use the specified structured output format version. This is
    intended for programs that invoke **notmuch(1)** internally. If
    omitted, the latest supported version will be used.

.. option:: --output=(sender|recipients|count)

    Controls which information appears in the output. This option
    can be given multiple times to combine different outputs.
    When neither --output=sender nor --output=recipients is
    given, --output=sender is implied.

    **sender**
        Output all addresses from the *From* header.

        Note: Searching for **sender** should be much faster than
        searching for **recipients**, because sender addresses are
        cached directly in the database whereas other addresses
        need to be fetched from message files.

    **recipients**
        Output all addresses from the *To*, *Cc* and *Bcc*
        headers.

    **count**
        Print the count of how many times was the address
        encountered during search.

        Note: With this option, addresses are printed only after
        the whole search is finished. This may take long time.

.. option:: --sort=(newest-first|oldest-first)

    This option can be used to present results in either
    chronological order (**oldest-first**) or reverse chronological
    order (**newest-first**).

    By default, results will be displayed in reverse chronological
    order, (that is, the newest results will be displayed first).

    This option is not supported with --output=count.

.. option:: --exclude=(true|false)

    A message is called "excluded" if it matches at least one tag in
    search.tag\_exclude that does not appear explicitly in the
    search terms. This option specifies whether to omit excluded
    messages in the search process.

    The default value, **true**, prevents excluded messages from
    matching the search terms.

    **false** allows excluded messages to match search terms and
    appear in displayed results.
