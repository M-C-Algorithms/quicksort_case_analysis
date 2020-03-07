# quicksort_case_analysis
Average case analysis of quicksort

Project 3 Average Case Analysis of Quicksort
To show that occasionally we are interested in the average case behavior for an algorithm,
let's look at the average case behavior of quicksort.
This project requires you to nicely write up, with all details explained, the entire proof
that is sketched below. You should just write on your own paper your \proofs" for each
claim made that is marked with ) in the left margin. When you are asked to do something
involving sums, it is good enough to write out enough terms that you realize what is going
on and that the claim is in fact true. We're asking for insight, not mathematical formalism.
Quicksort is a famous divide-and-conquer algorithm. It is well-known that for any partic-
ular strategy for picking the pivot item in the partition algorithm|say picking the rst
item in the list to be partitioned|quicksort can have worst-case behavior in 
(n2). So,
why does the algorithm continue to nd favor? We will present a proof that quicksort has
(n log n) average-case performance.
Let A(n) be the average time for quicksort to sort n items and nd a recurrence relation
for this function, which we will then solve.
We assume that given n items to partition, all n are equally likely. So,
A(n) =
Xn
p=1
1
n
[A(p 􀀀 1) + A(n 􀀀 p)] + n 􀀀 1:
This is true because each of the n possible choices of pivot item location is equally likely,
each with a probability of 1=n, and the partition time is n􀀀1 independent of the location
of the pivot time, on average, and A(p 􀀀 1) and A(n 􀀀 p) are the average times needed to
do the two recursive calls to quicksort on the two sublists produced by the partition.
Show that
Xn
p=1
[A(p 􀀀 1) + A(n 􀀀 p)] = 2
Xn
p=1
A(p 􀀀 1)
So,
A(n) =
2
n
Xn
p=1
A(p 􀀀 1) + n 􀀀 1:
So, we have the relationship
nA(n) = 2
Xn
p=1
A(p 􀀀 1) + n(n 􀀀 1):
Now we do a clever technique, using the same relationship with a dierent index, substi-
tuting n 􀀀 1 for n to obtain
(n 􀀀 1)A(n 􀀀 1) = 2
nX􀀀1
p=1
A(p 􀀀 1) + (n 􀀀 1)(n 􀀀 2):
Then we subtract these two equations, yielding
nA(n) 􀀀 (n 􀀀 1)A(n 􀀀 1) = 2A(n 􀀀 1) + n(n 􀀀 1) 􀀀 (n 􀀀 1)(n 􀀀 2) = 2A(n 􀀀 1) + 2(n 􀀀 1):
) Verify this algebra.
Now, tidy things up to yield
A(n)
n + 1
=
A(n 􀀀 1)
n
+
2(n 􀀀 1)
n(n + 1)
:
This might have all been pointless, except we sort of lucked out and the two A() terms
look the same, but with the argument shifted, so we can dene a new function by
B(n) =
A(n)
n + 1
;
and see that the previous equation gives a recurrence relation for B(n), namely
B(n) = B(n 􀀀 1) +
2(n 􀀀 1)
n(n + 1)
:
) Now we need to do our usual substitution technique to nd a pattern for B(n), and then
bound the resulting sum (which is neither a geometric series nor an arithmetic series, which
are pretty much the only ones we know how to add up exactly) by two integrals, both of
which integrate to some multiple of the natural logarithm of n. Thus, B(n) 2 (log n), so
A(n) 2 (n log n), by the denition of B(n).
