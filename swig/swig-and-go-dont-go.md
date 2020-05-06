# SWIG and Go don't Go

SWIG generates an awful lot of boiler plate code to wrap C functions in what
looks like an attempt to ensure memory is properly managed. When combined with
a C API that's anything more than simple (such as a C function returning a
pointer to heap allocated memory) SWIG doesn't really understand what's going
on and you have to step in with typemaps to correctly handle the memory.

Moreover, the Go that SWIG generates is really horrid and quite the opposite
to idiomatic Go that one would expect in a production Go application.

SWIG might be appropriate for other languages looking to directly use 
constructs in a C/C++ library but with respect to Go, it's not worth it 
considering the wonderful support provided to us by the Go developers through
cgo.