To make replying to email easier, :command:`notmuch reply` takes an existing
set of messages and constructs a suitable mail template. The :mailheader:`Reply-to`
header (if any, otherwise From:) is used for the :mailheader:`To` address. Unless
:option:`--reply-to=sender <notmuch reply --reply-to>` is specified, values from the
:mailheader:`To` and :mailheader:`Cc` headers
are copied, but not including any of the current user's email addresses
(as configured in primary\_mail or other\_email in the .notmuch-config
file) in the recipient list.

It also builds a suitable new subject, including Re: at the front (if
not already present), and adding the message IDs of the messages being
replied to to the References list and setting the :mailheader:`In-Reply-To` field
correctly.

Finally, the original contents of the emails are quoted by prefixing
each line with '> ' and included in the body.

The resulting message template is output to stdout.

See :ref:`search-terms` for details of the supported syntax for `<search-terms>`.

.. Note:: It is most common to use `notmuch reply` with a search string
    matching a single message, (such as id:<message-id>), but it can be
    useful to reply to several messages at once. For example, when a series
    of patches are sent in a single thread, replying to the entire thread
    allows for the reply to comment on issues found in multiple patches. The
    default format supports replying to multiple messages at once, but the
    JSON and S-Expression formats do not.
