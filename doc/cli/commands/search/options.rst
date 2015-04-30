.. program:: notmuch search

.. option:: --format=(json|sexp|text|text0)

  Presents the results in either JSON, S-Expressions, newline
  character separated plain-text (default), or null character
  separated plain-text (compatible with :manpage:`xargs(1)` -0 option
  where available).

.. option:: --format-version=N

  Use the specified structured output format version. This is
  intended for programs that invoke :command:`notmuch` internally. If
  omitted, the latest supported version will be used.

.. option:: --output=(summary|threads|messages|files|tags)

  **summary**
      Output a summary of each thread with any message matching
      the search terms. The summary includes the thread ID, date,
      the number of messages in the thread (both the number
      matched and the total number), the authors of the thread and
      the subject.

  **threads**
      Output the thread IDs of all threads with any message
      matching the search terms, either one per line
      (--format=text), separated by null characters
      (--format=text0), as a JSON array (--format=json), or an
      S-Expression list (--format=sexp).

  **messages**
      Output the message IDs of all messages matching the search
      terms, either one per line (--format=text), separated by
      null characters (--format=text0), as a JSON array
      (--format=json), or as an S-Expression list (--format=sexp).

  **files**
      Output the filenames of all messages matching the search
      terms, either one per line (--format=text), separated by
      null characters (--format=text0), as a JSON array
      (--format=json), or as an S-Expression list (--format=sexp).

      Note that each message may have multiple filenames
      associated with it. All of them are included in the output
      (unless limited with the --duplicate=N option). This may
      be particularly confusing for `folder:` or `path:`
      searches in a specified directory, as the messages may
      have duplicates in other directories that are included in
      the output, although these files alone would not match the
      search.

  **tags**
      Output all tags that appear on any message matching the
      search terms, either one per line (--format=text), separated
      by null characters (--format=text0), as a JSON array
      (--format=json), or as an S-Expression list (--format=sexp).

.. option:: --sort=(newest-first|oldest-first)

  This option can be used to present results in either
  chronological order (`oldest-first`) or reverse chronological
  order (`newest-first`).

  Note: The thread order will be distinct between these two
  options (beyond being simply reversed). When sorting by
  `oldest-first` the threads will be sorted by the oldest
  message in each thread, but when sorting by `newest-first` the
  threads will be sorted by the newest message in each thread.

  By default, results will be displayed in reverse chronological
  order, (that is, the newest results will be displayed first).

.. option:: --offset=[-]N

  Skip displaying the first N results. With the leading '-', start
  at the Nth result from the end.

.. option:: --limit=N

  Limit the number of displayed results to N.

.. option:: --exclude=(true|false|all|flag)

  A message is called "excluded" if it matches at least one tag in
  :term:`search.exclude_tags` that does not appear explicitly in the
  search terms. This option specifies whether to omit excluded
  messages in the search process.

  The default value, **true**, prevents excluded messages from
  matching the search terms.

  **all** additionally prevents excluded messages from appearing
  in displayed results, in effect behaving as though the excluded
  messages do not exist.

  **false** allows excluded messages to match search terms and
  appear in displayed results. Excluded messages are still marked
  in the relevant outputs.

  **flag** only has an effect when :option:`--output=summary <--output>`. The
  output is almost identical to **false**, but the "match count"
  is the number of matching non-excluded messages in the thread,
  rather than the number of matching messages.

.. option:: --duplicate=N

  For :option:`--output=files <--output>`, output the Nth filename associated
  with each message matching the query (N is 1-based). If N is
  greater than the number of files associated with the message,
  don't print anything.

  For :option:`--output=messages <--output>`, only output message IDs of messages
  matching the search terms that have at least N filenames
  associated with them.

  Note that this option is orthogonal with the **folder:** search
  prefix. The prefix matches messages based on filenames. This
  option filters filenames of the matching messages.
