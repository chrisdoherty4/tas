# Basic SWIG

There are lots of examples in the [SWIG source code](https://github.com/swig/swig/tree/master/Examples).

A basic SWIG interface file.

```
%module add

%inline %{
int add(int a, int b);
%}
```

By default, SWIG tries to manage the memory between the 2 languages by
allocating memory on the heap and copying argument values to it. Additionally, 
SWIG will allocate heap memory and copy the return value of a C API call
providing a pointer to the newly allocated memory in the target language.
