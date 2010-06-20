===================================
A sprintf Javascript implementation
===================================

Scope
=====

This document describes the capabilities and calling conventions of quite
complete sprintf implementation for Javascript. It does not explain made design
decisions or inner workings of the implementation.


Capabilities
============

This library does provide an almost complete reimplementation of the sprintf
function known from the standard c library.

The following datatypes are supported:

%%:
    A literal percent sign
%b:
    A binary number
%c:
    An ASCII character represented by the given value
%d:
    A signed decimal number
%f:
    A floating point value
%o:
    An octal number
%s:
    A string
%x:
    A hexadecimal number (lowercase characters)
%X:
    A hexadecimal number (uppercase characters)


All of the usual formatting flags are supported as well. Therefore you may
specify the algebraic sign, padding, alignment, width and precision. The syntax
is equivalent to the one used by the sprintf c function.


Usage
=====

After the corresponding Javascript file has been loaded, the global function
``sprintf`` is registered, ready to be called. Furthermore the String object is
extended with a ``printf`` method. Both of these are different means to execute
the same functionality.

You may either use the global function ``sprintf`` which returns the newly
formatted string if supplied with the format string, as well as all needed
arguments::

    var formatted = sprintf("The number is %.2f", number);

Or you may use the ``printf`` method directly on the format string::

    var formatted = "The number is %.2f".printf(number);

Internally the exactly the same processing takes place. Therefore you may
decide freely which syntax you like better.


License
=======

This library is licensed under the `MIT License`__

__ http://www.opensource.org/licenses/mit-license.html
