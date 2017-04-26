## Garbage Collection

### History

Garbage collection was invented by John McCarthy [for the original LISP implementation on the IBM 704](http://www-formal.stanford.edu/jmc/recursive.html) (1958).

### Well-known implementations

#### Boehm

### Distinguishing factors

#### Concurrent vs. blocking (‘stop the world’)

#### Support for finalization and resurrection

#### GC triggers

##### Out of memory

This is the traditional method. When the program tries to allocate some memory and cannot, a reclamation cycle is started to free up memory.

This is simple but there are some disadvantages:

* Memory must be reclaimed when the program is performing operations, rather than during any period of downtime.
* There will be more memory to reclaim and more work to do than if it were reclaimed earlier.
* In languages with finalizers, the finalizers may be delayed a long time before they are invoked, if the program is not allocating much memory.

Generational GC counters these problems due to having a small initial generation. This will fill up faster and so there will be less work to do and finalizers will be invoked more promptly.

##### Incremental