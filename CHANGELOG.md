# 0.3

Switch to a stream processing model.

This library is designed to have minimal dependencies, so we now have
a bespoke implementation of a cross between the pipes and machines
libraries included.

This change was done to make some parsing
operations easier, believe it or not. For example, most pre-processing
is done on a line-by-line basis, but we must also support macro
function applications that cross line boundaries. Thus the expansion
logic can not merely be given one line at a time from an input
file. Previously, a heuristic tried to combine consecutive lines
before the parsing stage. Now, the parser itself is able to pull
tokens in across lines when necessary.

TL;DR: The upshot is that processing `/usr/include/stdio.h` on OS X (a
surprisingly complicated file!)  now uses 78% of the time and 0.38%
the memory of previous versions of `hpp`.

# 0.1

First release!
