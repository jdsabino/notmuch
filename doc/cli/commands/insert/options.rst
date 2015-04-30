.. program:: notmuch insert

.. option:: --folder=<folder>

    Deliver the message to the specified folder, relative to the
    top-level directory given by the value of **database.path**. The
    default is to deliver to the top-level directory.

.. option:: --create-folder

    Try to create the folder named by the ``--folder`` option, if it
    does not exist. Otherwise the folder must already exist for mail
    delivery to succeed.

.. option:: --keep

    Keep the message file if indexing fails, and keep the message
    indexed if applying tags or maildir flag synchronization
    fails. Ignore these errors and return exit status 0 to
    indicate succesful mail delivery.

.. options:: --no-hooks
    
    Prevent hooks from being run.
