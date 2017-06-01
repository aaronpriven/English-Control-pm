# NAME

English::Control - use names beginning with control for punctuation
variables

# SYNOPSIS

````perl
    use English::Control;
    if (${^ERRNO} =~ /denied/) { ... }
````

# DESCRIPTION

This module provides aliases for the built-in variables whose names no
one seems to like to read. Variables with side-effects which get
triggered just by accessing them (like $0) will still be affected.

Unlike the English module, the aliases created by this module begin with
a control character and thus will be always found in the main namespace
and are in the area reserved by perl for its own use, and don't clutter
your regular namespace.

For those variables that have an awk version, both long and short
English alternatives are provided. For example, the $/ variable can be
referred to either $^{RS} or ${INPUT_RECORD_SEPARATOR} if you are using
the English module.

See perlvar for a complete list of these.

Since control-character variables are forced to be in package main,
nothing is imported into the caller's namespace, and the
control-character aliases are made immediately upon compilation of this
module. There is no difference between

````perl
    use English::Control;
````

and


````perl
    use English::Control ();
````

# PERFORMANCE

    This module does not touch the match variables that slow down older
    versions of perl. The aliases ${^PREMATCH}, ${MATCH}, and ${^POSTMATCH}
    are provided by perl itself in more recent versions.

#AUTHOR

Aaron Priven <apriven@actransit.org>

# COPYRIGHT & LICENSE

Copyright 2017

 This program is free software; you can redistribute it and/or modify it
 under the terms of either:

 *   the GNU General Public License as published by the Free Software
     Foundation; either version 1, or (at your option) any later version,
     or

 *   the Artistic License version 2.0.

 This program is distributed in the hope that it will be useful, but
 WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
