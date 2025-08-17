# SYMBOL COMBINATION MATRIX (seed)
- `*` × `[]` × `+/-`  → pointer arithmetic/indexing aliasing
- `&` × `*`           → `*&p` vs `&*p`, array decay
- `?:` × `,`          → precedence traps (macros)
- `++/--` × `*`       → pre/post inc on deref’d lvalues
- `=, +=` × `volatile`→ side effects under O2/O3
- `<< >>` × signedness→ UB boundaries
- `.`/`->` × packed   → unaligned access risk
- `# ##` × `()`       → macro arg swallowing
