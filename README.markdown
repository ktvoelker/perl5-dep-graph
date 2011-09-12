
Perl 5 Module Dependency Grapher
================================

This tool will generate a dependency graph of your Perl modules. I run it like this:

  ./deps `find ./ -name '*.pm'` > out.dot

The output can be turned by Graphviz into an image:

  dot -T png -o out.png out.dot

Leaf nodes have rectangular outlines, while other nodes have elliptical outlines.
This is the result of the original purpose of this tool: planning a port of a
complicated Perl program to another object-oriented language.

