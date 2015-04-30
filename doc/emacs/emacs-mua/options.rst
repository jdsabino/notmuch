    ``-h, --help``
        Display help.

    ``--client``
        Use emacsclient, rather than emacs. This will start
        an emacs daemon process if necessary.

    ``-s, --subject=``\ <subject>
        Specify the subject of the message.

    ``--to=``\ <to-address>
        Specify a recipient (To).

    ``-c, --cc=``\ <cc-address>
        Specify a carbon-copy (Cc) recipient.

    ``-b, --bcc=``\ <bcc-address>
        Specify a blind-carbon-copy (Bcc) recipient.

    ``-i, --body=``\ <file>
        Specify a file to include into the body of the message.

    ``--no-window-system``
        Even if a window system is available, use the current terminal

    ``--print``
        Output the resulting elisp to stdout instead of evaluating it.

The supported positional parameters and short options are a compatible
subset of the **mutt** MUA command-line options.

Options may be specified multiple times.
