# & — address-of on objects vs rvalues
**Goal:** Show `&` requires an lvalue object; array name “decays” but `&arr` differs.

```c
#include <stdio.h>
int main(void){
    int x = 42;
    int *p = &x;          // OK: lvalue object
    int arr[3] = {1,2,3};
    printf("%p %p\n", (void*)arr, (void*)&arr); // different types/values
    // int *q = &(x+1);   // ERROR: not an lvalue object
    return printf("%d\n", *p);
}
