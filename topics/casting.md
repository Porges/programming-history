## Downcasting and Upcasting

The oldest reference I've found yet is from Sep 1990, in [a Usenet post](http://groups.google.com/group/gnu.g++.bug/msg/0f9930a029cf2657?dmode=source). This uses the term "castdown".

The library referenced there is the NIHCL ([available from the Software Preservation Group](http://www.softwarepreservation.org/projects/c_plus_plus/library/index.html#NIHCL)), which contains this code (`MI` is "multiple inheritance"):

```c++
#ifdef MI

#define DECLARE_CASTDOWN(classname) \
    static classname& castdown(Object& p) \
        { return *(classname*)(&p ? p._safe_castdown(*desc()) : 0); } \
    static const classname& castdown(const Object& p) \
        { return *(const classname*)(&p ? p._safe_castdown(*desc()) : 0); } \
    static classname* castdown(Object* p) \
        { return (classname*)(p ? p->_safe_castdown(*desc()) : 0); } \
    static const classname* castdown(const Object* p) \
        { return (const classname*)(p ? p->_safe_castdown(*desc()) : 0); } \

#else

#define DECLARE_CASTDOWN(classname) \
    static classname& castdown(Object& p)           { return (classname&)p; } \
    static const classname& castdown(const Object& p)   { return (const classname&)p; } \
    static classname* castdown(Object* p)           { return (classname*)p; } \
    static const classname* castdown(const Object* p)   { return (const classname*)p; } \

#endif
```

The book that this code was included with (*[Data Abstraction and Object-Oriented Programming in C++](http://books.google.co.nz/books?ei=S_kUT-rVEpCKmQXHrYXBAw&id=H5sZAQAAIAAJ&dq=%22Data+abstraction+and+object-oriented+programming+in+C%2B%2B%22+cast+down&q=%22castdown%22#search_anchor)*) also uses the term "castdown".

The term "castdown" also seems to predate "downcast", [at least on Usenet](http://groups.google.com/groups/search?safe=off&q=%22castdown%22&btnG=Search&as_mind=1&as_minm=1&as_miny=1981&as_maxd=31&as_maxm=12&as_maxy=1990&as_drrb=b&sitesearch=).
