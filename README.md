# format-rs
Simplified int &amp; float formatting routines

The default rust integer and floating point formatting routines require a huge
amount of stack space, which is unsuitable for embedded programming.

Measurements I made showed that calling println! requires approx 650 bytes
of stack, and calling println!("{}", 1); adds an additional 180 bytes of stack
on top of that.

For floating point, it requires an additional 1.5K (over the 650 bytes of base).

These routines format into an already allocated buffer which allows for reduced
heap usage.
