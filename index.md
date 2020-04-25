# Segment Trees
A segment tree is an organized set of ranges with 
stored results of combined operations. 
For example, with `a = [2, 5, 7, 2, 8, 5, 7]` 
and we store `sum(a[2:5]) = 17`
and we want to know `sum(a[1:7])`.
Instead of working out `sum(a[1:7]) = sum(a[1], a[2], a[3], a[4], a[5], a[6])`
we can simply work out `sum(a[1:7]) = sum(a[1], a[2:5], a[5], a[6])` assuming we already have `sum(a[2:5])` computed.
