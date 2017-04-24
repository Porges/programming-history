## Garbage Collection

### History

Wikipedia states that garbage collection was invented by John McCarthy.

### Well-known implementations

#### Boehm

### Distinguishing factors

#### Concurrent vs. blocking (‘stop the world’)

#### Support for finalization and resurrection

### Language specifics

#### Go

Finalization is supported (via [`runtime.SetFinalizer`](https://golang.org/pkg/runtime/#SetFinalizer)).

Finalizers are invoked in dependency order. Accordingly, if a reference cycle contains finalizers, the objects in the cycle are not guaranteed to be finalized nor collected.

Resurrection seems to be supported as finalization can be re-registered during finalization.

#### Java

Finalization is performed on non-user threads. Finalization order is not defined. Unhandled exceptions in finalizers are ignored.

Object resurrection is supported. Finalizers are only ever invoked once, even if an object is resurrected.

#### .NET

.NET supports two GC modes: workstation (optimized for responsiveness) and server (optimized for throughput). 

Finalization is performed on (a) dedicated thread(s). Finalization order is not defined.

Since .NET 2.0 (2005), unhandled exceptions in finalizers terminate the process.

Objects may be resurrected during finalization by creating a reference to them somewhere that is considered ‘alive’ (such as a static field). Resurrected objects may re-register for finalization by calling [`GC.ReRegisterForFinalize`](https://msdn.microsoft.com/en-us/library/system.gc.reregisterforfinalize.aspx).

Explicit finalizers should not be used in modern code. Classes that manage external resources should inherit from [`SafeHandle`](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.safehandle.aspx).

#### PHP

PHP ≥ 5.3 (2009) uses a hybrid reference-counted/GC approach. Most objects are destroyed due to going out of scope, and have their destructors (`__destruct`) invoked at that point. Destructors are called in dependency order unless the program is shutting down, in which case the order is undefined.

Objects that are caught in a reference cycle are periodically collected by GC. It is not specified what happens to destructors in this case.

#### Python

The main implemention (known as ‘CPython’) uses a hybrid reference-counted/GC approach. All objects are refcounted and most are destroyed as soon as they go out of scope. This also means that finalizers (methods called `__del__`) are run on the thread on which the object became unreferenced (this [can cause unexpected deadlocks in unwary code](http://carefully.understood.systems/blog-2017-04-19-bounded-log-queue.html)).

Objects that are caught in a reference cycle are periodically collected by GC. In CPython 2, if a cycle contains an object with a destructor, none of the objects are finalized or freed, and they are instead stored in a list ([`gc.garbage`](https://docs.python.org/2/library/gc.html)). In CPython ≥ 3.4 (2014), finalizers on all objects in a cycle are invoked in an arbitrary order. In addition, in CPython ≥ 3.4, finalizers are only ever invoked once, even if an object is resurrected.

Other implementations such as PyPy implement full GC as in other languages, and so finalization occurs on non-user threads. In order to maintain parity with CPython finalization semantics, [PyPy performs finalization in a ‘topological’ manner](https://morepypy.blogspot.com.au/2008/02/python-finalizers-semantics-part-1.html).