
Perl 5 Module Dependency Grapher
================================

This tool will generate a dependency graph of your Perl modules in Graphviz format.

Required command-line flags:

* `-d`: the directory containing the module files

Optional command-line flags:

* `-o`: the name of the output file (default to standard output)

* `-p`: a prefix which a module's name must have for it to be included

* `-x`: the name of a file containing a list of names of modules to exclude,
  one per line

Leaf nodes have rectangular outlines, while other nodes have elliptical outlines.
This is the result of the original purpose of this tool: planning a port of a
complicated Perl program to another object-oriented language.

Caveats:

* If an inclusion prefix is given (with `-p`), it must not contain any double
  colons.  This is a silly limitation which I ought to fix.

* The usual convention of one module per file is assumed.

* References to modules with no double colons in their names will be missed.

* References that don't appear literally in the source text will be missed.

* Text that looks like a module reference, but isn't, may be mistaken for one. So
hopefully you don't use double colons just for fun.

