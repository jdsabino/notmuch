Output is to the given filename, if any, or to stdout.

These tags are the only data in the notmuch database that can't be
recreated from the messages themselves. The output of notmuch dump is
therefore the only critical thing to backup (and much more friendly to
incremental backup than the native database files.)

See **notmuch-search-terms(7)** for details of the supported syntax
for <search-terms>. With no search terms, a dump of all messages in
the database will be generated. A "--" argument instructs notmuch that
the remaining arguments are search terms.
