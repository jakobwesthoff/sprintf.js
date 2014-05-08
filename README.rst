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

The functionallity is exposed as a CommonJS module (nodejs), an AMD Module (requirejs) or as a global function, based on the environment it is used in.

It may either be used as a standalone function, or attached to the string prototype:

    // Global function
    var formatted = sprintf("The number is %.2f", 42);

    // CommonJS
    var sprintf = require("./path/to/sprintf");
    var formatted = sprintf("The number is %.2f", 42);

    // AMD
    define("your-module", ["./path/to/sprintf"], function(sprintf) {
        var formatted = sprintf("The number is %.2f", 42);
    });

The addition to the `String.prototype` is not done automatically to not interfere with a language primitive. You may however add a `printf` function to every string by calling `.attach`:

    // Load sprintf as shown above
    sprintf.attach(String.prototype);

    // Now every string has a printf function available
    var formatted = "%s %s".printf("foo", "bar");


License
=======

This library is licensed under the `MIT License`__

__ http://www.opensource.org/licenses/mit-license.html
