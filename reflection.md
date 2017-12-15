HPCE CW6 Individual Reflection
==============================

Imperial login : har14

Github login : h22roscoe

CW5 group : Baozi

CW6 group : Baozi

Cohort : DOC4

Guidance
--------

_The goal of this component is to get people to think about what they
have learnt in an individual sense, and to try to think about how
this course has developed or changed your own skills, knowledge, and/or attitudes.
This section is individually marked, so I (m8pple) will look at
every single submitted `reflection.md` and evaluate it. There may
or may not be feedback provided on this component (and if there is,
it will come way off in Feb or something). Usually most people will say
something sensible and realistic, which is the main point, and
serves as immediate feedback in and of itself. I'm most likely
to comment if the points made are particularly good, or particularly
vague, generic, dismissive. Ideally these should be specific to an individual,
not to a group, so I suggest doing it alone._

_There is no hard marks schema (I moderate across the cohort),
no example answers, and I'm not seeking a specific answer. A response
given by one student might be excellent, but almost the same response by
another might look quite weak - it all depends on individual context.
Each of the 50 word responses is weighted equally._

_A possible response to some questions could be: "I haven't learnt
anything, I already knew how to do it." That's awesome, presumably
made this course very easy, and should be reflected in the
performance-oriented marks for CW5+CW6. Not everyone gets something from the
course: some people just need to get marks or pick something they already
know how to do. Those who already knew the content or have covered it in
other courses should (theoretically) cruise through. An entirely intentional
aspect of this component is that those who already have the most experience
will need to work that bit harder to justify why and where they have learnt
something._

_The load of this component is expected to be at most an hour per
person, and up to 500 words. *You do not need to write 500 words to
get good marks.* The 50 word limit per answer [is mainly to encourage
specific-ness and reduce work-load](https://github.com/HPCE/hpce-2017-cw6/issues/42)._

Connections with existing courses and knowledge
===============================================

_Which courses that you took in previous years did you think this course was most related to,
and why? These could be courses in any department or any university._

Of the courses I have taken previously, the course that is most related is the
C++ course that we did in second year computing. This is obviously because the
code was written in C++. There was also a concurrency course which was relevant
for understanding race conditions.

_What relevant pre-existing skills and existing knowledge did you bring to the course?_

I knew how to program (in C++ to an extent) and how to use git. I was also familiar
with Github, so the fact that this course used it as the main form of communication
worked well for me. I also knew about race conditions and concurrency from other courses.

What have you learnt in the course? : practise
==============================================

_What has been the most useful practical skill you have acquired in this course?_

This course has been useful for understanding how to optimise programs for a GPU
and for learning TBB to parallelise programs. The most useful skill in my opinion
is learning how and when to optimise for a GPU.

_When would it have been useful in your own past activities?_

I haven't yet had the right opportunity to use parallelisation. Most of the programs
that I have written have not been very complex or have been written in languages
which come with their own runtime environments.

_When do you anticipate it might be useful in the future?_

I had planned on making a video game engine at some point which I imagine would be
fairly low-level programming that would hopefully be highly optimised for GPUs.
This would be where I expect knowing a library like OpenCL would be useful.

_What practical aspect (e.g. TBB, OpenCL, AWS, shell, ...) do you think is
 the *least* likely to be useful, and why?_

TBB, and this is because most of the programs I am likely to see will not be written
in C++ nor will they have the need to be parallelised. Knowing AWS is likely to
be important in most modern software jobs and knowing about shell commands is vital.

What have you learnt in the course? : theory/concepts
=====================================================

_How has the course changed your understanding of how to accelerate
or improve program performance?_

I don't think the course has changed my understanding of how to improve program
performance in that I already knew these optimisations were possible. What this
course has taught me is how to actually go about doing it.

_What is a specific example of tuning agglomeration *you* encountered or resolved in CW5 or CW6? Where
 possible, refer to a commit and source file (e.g. embed a link)._

There was one instance in CW6 where it was spotted that one particular test in Rabbit
(Stress) was a significant proportion of total time so we changed our implementation
from all separate tasks to just two separate tasks - the big test and the rest.

[The commit](https://github.com/HPCE/hpce-2017-cw6-Baozi/commit/ae70a2f1d21f99ec291fd4dab53d62297ef93396)

_What is a specific example of managing critical path that *you* encountered or resolved in CW5 or CW6?
 Where possible, refer to a commit and source file._

We do think that the Multinom test part of Rabbit is an issue of managing critical
path that we have encountered so far. This is because if we parallelise all parts
into equal tasks we will still have a bottleneck of Multinom holding back the
completion of the suite.

_What is a specific example of balancing communication vs computation cost from CW5 or CW6?
 Where possible, refer to a commit and source file._

With mining in CW5 we used OpenCL and we needed to find a balance of communication
and computation cost. We realised it wasn't worth using using the GPU for a single
run of TEA_hash but it was worth running in the GPU if we could run in batches and
to do this we tried to make the OpenCL code generate the next random number. 
