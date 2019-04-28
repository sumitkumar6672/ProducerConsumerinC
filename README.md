# ProducerConsumerinC
Producer and Consumer Problem

## Problem
Q. Consider a producer-consumer situation, where a process P produces an integer using the
function produceNext() and sends it to process C. Process C receives the integer from P and
consumes it in the function consumeNext(). After consuming this integer, C must let P know,
and P must produce the next integer only after learning that C has consumed the earlier one.
Assume that P and C get a pointer to a shared memory segment of 8 bytes, that can store any two
4-byte integer-sized fields, as shown below. Both fields in the shared memory structure are
zeroed out initially. P and C can read or write from it, just as they would with any other data
object. Briefly describe how you would solve the producer-consumer problem described above,
using only this shared memory as a means of communication and synchronization between
processes P and C. You must not use any other synchronization or communication primitive.
You are provided template code below which gets a pointer to the shared memory, and
produces/consumes integers. You must write the code for communicating the integer between
the processes using the shared memory, with synchronization logic as required.

```
struct shmem_structure { int field1; int field2; };
(a) Producer:
struct shmem_structure *shptr = get_shared_memory_structure();
while(1) { int produced = produceNext(); }
(b) Consumer: struct shmem_structure *shptr = get_shared_memory_structure(); while(1) { int
consumed; //fill this value from producer consumeNext(consumed); }
```