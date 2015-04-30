This command is used to import tags previously exported using :command:`notmuch dump`.
The input is read from the given filename, if any, or from stdin.

:command:`notmuch restore` will detect if the input is compressed in
:manpage:`gzip(1)` format and automatically decompress it while reading. This
detection does not depend on file naming and in particular works for
standard input.
