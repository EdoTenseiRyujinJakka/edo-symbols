# `->` — member access through pointer

**Goal:** Demonstrate how `ptr->m` works, its equivalence to `(*ptr).m`, and the common traps (null/dangling, packed/unaligned, precedence).

---

## ✅ Minimal Example

```c
#include <stdio.h>

struct P { int a; int b; };

int main(void){
    struct P s = {1, 2};
    struct P *p = &s;

    // same value via pointer/member vs direct/member
    printf("%d %d %d\n", s.a, p->a, (*p).b);   // 1 1 2

    // equivalence identity
    printf("%s\n", (p->b == (*p).b) ? "eq" : "neq");

    // precedence: -> binds tighter than *
    // *p->a  == *(p->a)  (type: int, but UB because p->a is not a pointer)
    // (*p).a == p->a     (correct)
    printf("%d\n", (*p).a);
}
