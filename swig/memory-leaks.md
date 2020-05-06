# Memory Leaks

If you have a C API call that returns a pointer to some managed memory SWIG
will attempt to copy that memory to a newly allocated piece of memory by default.
This results in a memory leak when there is a corresponding `free` style call
to the original C API call.

```c
const char * DoAThing();
void FreeAThing(const char *thing);
```

You can patch the memory leak using a [typemap](http://www.swig.org/Doc4.0/Typemaps.html#Typemaps).

```
typemap(ret) const char *
%{  
    FreeAThing($1);
%}
```