readme

This project tries to simulate data that varies number of trials and the number of
participants to try to get a sense of what smaller N but higher trials per 
participant might look like formally. 

The motivation for doing so follows from reading these three papers:

1) Power contours: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8329985/

2) Small is Beautiful: https://doi.org/10.3758/s13423-018-1451-8

3) Event history analysis: https://doi.org/10.1177/2041669520978673

The first two for obvious reasons, as they show that "power" emerges from sample 
size and trial count. And depending on the structure of the data, one or the other
can be more influential in determining power.

The third paper because when we interviewed Sven, he used EHA, and I wasn't sure
how power or precision would be estimated in those types of analyses. This is 
because you have block (if time is binned) by other factors. So the analysis could
be rather complex in terms of design etc. e.g., 14 bins by however many other 
factors.

So, the aim here is to become more familiar estimating power/precision as a function 
of sample size and trial count in the types of designs that we might typically use.

## chronology ##

I started with the sims.Rmd file. Things got complicated quickly (see notes in the 
file). So I then took a different and simpler approach with sims_simple.Rmd.

sims_simple.Rmd did the following:

- load past RT data used in sim1 of the power contours paper
- build a multi-level model with a simple cong vs incog design
- use the values generated from the model to then simulate many datasets and see
if we can simulate multi-level data that has a similar power estimates as power
contours. That is, that power varies according to N and K as we might expect it to
based on the structure of the data.
- I did this for two effect sizes - one similar to the original ~50ms and one
half of that ~25ms.


note - to save time, I didn't build models. I just calculated 95%CI and used that
as a quick guide to power.