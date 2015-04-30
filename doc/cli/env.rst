The following environment variables can be used to control the behavior
of notmuch.

.. envvar:: NOTMUCH_CONFIG

    Specifies the location of the notmuch configuration file. Notmuch
    will use :file:`${HOME}/.notmuch-config` if this variable is not set.


.. envvar:: NOTMUCH_TALLOC_REPORT

    Location to write a talloc memory usage report. See
    :ref:`talloc_enable_leak_report_full` in :manpage:`talloc(3)` for more
    information.

.. envvar:: NOTMUCH_DEBUG_QUERY

    If set to a non-empty value, the notmuch library will print (to
    stderr) Xapian queries it constructs.
