The input must consist of lines of the format:

+<*tag*\ >\|-<*tag*\ > [...] [--] <*query*\ >

Each line is interpreted similarly to **notmuch tag** command line
arguments. The delimiter is one or more spaces ' '. Any characters in
<*tag*\ > **may** be hex-encoded with %NN where NN is the hexadecimal
value of the character. To hex-encode a character with a multi-byte
UTF-8 encoding, hex-encode each byte. Any spaces in <tag> **must** be
hex-encoded as %20. Any characters that are not part of <*tag*\ > **must
not** be hex-encoded.

In the future tag:"tag with spaces" style quoting may be supported for
<*tag*\ > as well; for this reason all double quote characters in
<*tag*\ > **should** be hex-encoded.

The <*query*\ > should be quoted using Xapian boolean term quoting
rules: if a term contains whitespace or a close paren or starts with a
double quote, it must be enclosed in double quotes (not including any
prefix) and double quotes inside the term must be doubled (see below for
examples).

Leading and trailing space ' ' is ignored. Empty lines and lines
beginning with '#' are ignored.

EXAMPLE
-------

The following shows a valid input to batch tagging. Note that only the
isolated '\*' acts as a wildcard. Also note the two different quotings
of the tag **space in tags**

::

    +winner *
    +foo::bar%25 -- (One and Two) or (One and tag:winner)
    +found::it -- tag:foo::bar%
    # ignore this line and the next

    +space%20in%20tags -- Two
    # add tag '(tags)', among other stunts.
    +crazy{ +(tags) +&are +#possible\ -- tag:"space in tags"
    +match*crazy -- tag:crazy{
    +some_tag -- id:"this is ""nauty)"""
