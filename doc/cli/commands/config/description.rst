    **get**
        The value of the specified configuration item is printed to
        stdout. If the item has multiple values (it is a list), each
        value is separated by a newline character.

    **set**
        The specified configuration item is set to the given value. To
        specify a multiple-value item (a list), provide each value as a
        separate command-line argument.

        If no values are provided, the specified configuration item will
        be removed from the configuration file.

    **list**
        Every configuration item is printed to stdout, each on a
        separate line of the form:

        *section*.\ *item*\ =\ *value*

        No additional whitespace surrounds the dot or equals sign
        characters. In a multiple-value item (a list), the values are
        separated by semicolon characters.
