
Perl 5 Module Dependency Grapher
================================

This tool will generate a dependency graph of your Perl modules. I run it like this:

    ./deps `find ./ -name '*.pm'` > out.dot

The output can be turned by Graphviz into an image:

    dot -T png -o out.png out.dot

Leaf nodes have rectangular outlines, while other nodes have elliptical outlines.
This is the result of the original purpose of this tool: planning a port of a
complicated Perl program to another object-oriented language.

Caveats:

* Run this from the root directory of your project. The tool assumes the usual
convention of one module per file and determines the file's module name by transforming
the file name as given on the command line.

* References to modules with no double colons in their names will be missed.

* References that don't appear literally in the source text will be missed.

* Text that looks like a module reference, but isn't, may be mistaken for one. So
hopefully you don't use double colons just for fun.

