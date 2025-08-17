# `*` — Dereference and Identity

**Goal:** Show that `*` is the dereference operator, how it interacts with pointer identity, and where confusion arises.

---

## ✅ Minimal Example

```c
#include <stdio.h>

int main(void) {
    int x = 99;
    int *p = &x;

    printf("x = %d\n", x);        // direct
    printf("*p = %d\n", *p);      // dereference
    printf("&x == p ? %s\n", (&x == p) ? "yes" : "no");
    printf("&*p == p ? %s\n", (&*p == p) ? "yes" : "no");  // always true (if p valid)
    printf("*&x == x ? %s\n", (*&x == x) ? "yes" : "no");  // always true
}
