Implementation:
Our general approach was to iteratively add functionality from
the paper, starting with the simplest tasks and building up
from there. We implement RAFT to spec, keeping all of the 
different pieces of state as global variables in the script.
We split out each RPC request/response into its own helper 
method, with more helpers to do things like commiting log entries,
etc.

Difficulties:
We experienced a number of difficulties in implementing this 
assignment. What was very interesting was that our code 
passed all tests when using time.clock() instead of time.time(),
without implementing any of the additional restrictions in section 
5.4.1. We believe that this is because the most active replica
would time out first, meaning that it would have the most up-to-
date logs, and the tests would succeed. 

Testing:
We used the testing scripts and printouts, narrowing down
on any problems that we had and simplifying the problem as 
much as possible to debug.
