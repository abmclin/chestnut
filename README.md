# Chestnut Lisp->C Translator
an Common Lisp implementation

## History

From Bill Brodie <wbrodie@panix.com>: (https://groups.google.com/forum/#!msg/comp.lang.lisp/nYMJWmpkToY/fgtu8zkHxYgJ)

I founded Chestnut and produced the first version of the Lisp-to-C
translator, which covered a small subset of Common Lisp, for in-house
use in 1989.  Chestnut was working on A.I.-flavored applications,
particularly a natural-language engine, that we wanted to code in Lisp
-- but had to deliver in C, mostly for memory compactness.  Since the
C code would at some point be maintained, and there were Lisp-agnostic
C programmers on the project, we wanted the code to be as clean and
clear as possible.  Soon after, we discovered that there was a
significant demand for the translator itself.
The company's encounter with the market, beginning in 1990, was quite
a shock: We assumed that customers would adapt their Lisp code to use
our Common Lisp subset, to explicitly garbage-collect, etc.  We wound
up implementing all of CLtL2, including CLOS, and created several
translation modes, one of which was fully automatic; local variables
were saved on a stack so that they could be recognized as roots for
garbage collection.  A good number of large Lisp projects were coming
to fruition at about the same time, and had to deliver in C for
various reasons: portability; to work with multilingual teams;
performance and memory footprint; and general fears about Lisp as a
language.  Many of them became Chestnut customers.

The project benefited greatly from the work of a small group of Lisp
internals experts, including several members of the ANSI Lisp (X3J13)
standards committee, which had codified Common Lisp only recently.
Kim Barrett wrote all of the CLOS translator; Sandra Loosemore
designed the translation engine and optimization framework; Jonathan
Rees wrote much of the runtime library; he and James O'Toole, both MIT
grad students, wrote several very fast garbage collectors, did a good
deal of optimizing, and worked on portability; Andy Latto, Dmitry
Nizhegorodov, Jeff Brodie, and Rick Harris made major contributions.
Jim Allard, then with Gensym Corp., had built a translator for
Gensym's use that Chestnut eventually replaced, and already had a lot
of good engineering ideas that were incorporated into the product.

The translator was a pricey product: the company provided customers a
good deal of support, and for customers who wanted readable C code
that was also fast, compact, and portable, didn't really have any
competitors.  Our customers' best alternative was usually to spend
several million dollars, and a year or two, reimplementing their
applications in C.  So Chestnut was able to find a niche, which grew
as the company expanded its marketing efforts and as the amount of pre-
sale engineering work it needed to perform for each customer
drastically fell.

The company went out of business in 1995, several years after I left.
The reason wasn't really price; it was that the board didn't contain
enough members who understood Chestnut's customers, mostly research
groups, or its products, which were highly technical.  Unable to
effectively balance engineering, support, and marketing, even on a
small scale, the company lost sales it could have made, alienated some
early customers who were among its strongest "success story"
references, and failed to form relationships with Lisp vendors and
other natural allies.  Over time, these defects became fatal.

Its technology was sold to Oracle for use on a single development
project.  It's possible that an approach by the Lisp community would
persuade Oracle to release the software as open source.  Or Gensym,
now based in Texas, might consent to its release.  It would take some
legwork and luck.  In its favor are the passage of time and the re-
emergence of Lisp as a platform.

The closest heir to Chestnut's technology seems to be Thinlisp, about
which more above.  Led by Jim Allard and Ben Hyde, it starts with some
of the same design philosophy as Chestnut and focuses on the
engineering virtues that, in the developers' experience, were most
critical to a successful "develop in Lisp, deploy in C" engine.
