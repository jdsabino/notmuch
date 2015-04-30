This can both reduce the space required by the database and improve
lookup performance.

The compacted database is built in a temporary directory and is later
moved into the place of the origin database. The original uncompacted
database is discarded, unless the
:option:`--backup=<directory>` option is used.

.. Note::
   that the database write lock will be held during the compaction
   process (which may be quite long) to protect data integrity.
