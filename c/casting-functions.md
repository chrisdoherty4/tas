# Casting callbacks

When casting in C, you can generally tell the compiler some memory is of any type. It's particularly troublesome when you have callbacks.

Pseudo example
```
typedef void (CallFoo*)(const char*);
typedef void (CallBar*)(int);

void CallMe(CallFoo foo, CallBar bar);

void Foo(const char*) { ... }
void Bar(int) { ... }

int main() {
    # Call casting the wrong way round.
    CallMe((CallBar) &Foo, (CallFoo) &Bar); 

    return 0;
}
```
