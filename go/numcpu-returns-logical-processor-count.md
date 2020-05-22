# NumCPU Returns Logical Core Count

Several books claim the `runtime.NumCPU()` function in Go returns the total
number of physical processors; this isn't true.

The Go documentation has always stated the `NumCPU()` function returns the 
total number of _logical processors_. Perhaps the terminology is used 
interchangably by authors but it's misleading.

```go
package main

import (
    "runtime"
    "fmt"
)

func main() {
    fmt.Println(runtime.NumCPU())
}
```