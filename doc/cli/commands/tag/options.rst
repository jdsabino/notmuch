.. program:: notmuch tag

.. option:: --remove-all

  Remove all tags from each message matching the search terms
  before applying the tag changes appearing on the command line.
  This means setting the tags of each message to the tags to be
  added. If there are no tags to be added, the messages will have
  no tags.

.. option:: --batch

  Read batch tagging operations from a file (stdin by default).
  This is more efficient than repeated **notmuch tag**
  invocations. See `TAG FILE FORMAT <#tag_file_format>`__ below
  for the input format. This option is not compatible with
  specifying tagging on the command line.

.. option:: --input=<filename>

  Read input from given file, instead of from stdin. Implies
  :option:`--batch`.
