.. program:: notmuch reply

.. option:: --format=(default|json|sexp|headers-only)

  **default**
      Includes subject and quoted message body as an :RFC:`2822`
      message.

  **json**
      Produces JSON output containing headers for a reply message
      and the contents of the original message. This output can be
      used by a client to create a reply message intelligently.

  **sexp**
      Produces S-Expression output containing headers for a reply
      message and the contents of the original message. This
      output can be used by a client to create a reply message
      intelligently.

  **headers-only**
      Only produces In-Reply-To, References, To, Cc, and Bcc
      headers.

.. option:: --format-version=N

  Use the specified structured output format version. This is
  intended for programs that invoke  :command:`notmuch` internally. If
  omitted, the latest supported version will be used.

.. option:: --reply-to=(all|sender)

  **all** (default)
      Replies to all addresses.

  **sender**
      Replies only to the sender. If replying to user's own
      message (Reply-to: or From: header is one of the user's
      configured email addresses), try To:, Cc:, and Bcc: headers
      in this order, and copy values from the first that contains
      something other than only the user's addresses.

.. option:: --decrypt

  Decrypt any MIME encrypted parts found in the selected content
  (ie. "multipart/encrypted" parts). Status of the decryption will
  be reported (currently only supported with :option:`--format=json <--format>` and
  :option:`--format=sexp <--format>`) and on successful decryption the
  multipart/encrypted part will be replaced by the decrypted
  content.

  Decryption expects a functioning :manpage:`gpg-agent(1)` to provide any
  needed credentials. Without one, the decryption will fail.
