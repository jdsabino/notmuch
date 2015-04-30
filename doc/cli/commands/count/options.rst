.. program:: notmuch count

.. option:: --output=(messages|threads|files)

  **messages**
      Output the number of matching messages. This is the default.

  **threads**
      Output the number of matching threads.

  **files**
      Output the number of files associated with matching
      messages. This may be bigger than the number of matching
      messages due to duplicates (i.e. multiple files having the
      same message-id).

.. option:: --exclude=(true|false)

  Specify whether to omit messages matching search.tag\_exclude
  from the count (the default) or not.

.. option:: --batch

  Read queries from a file (stdin by default), one per line, and
  output the number of matching messages (or threads) to stdout,
  one per line. On an empty input line the count of all messages
  (or threads) in the database will be output. This option is not
  compatible with specifying search terms on the command line.

.. option:: --input=<filename>

  Read input from given file, instead of from stdin. Implies
  ``--batch``.

