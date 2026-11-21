## Audit a parent and child table before import

Returns [load acceptable, duplicate parent rows, orphan child rows, first orphan row]. This local check complements database-enforced constraints. Invalid arguments and nonfinite results return an empty vector.

1. Open an empty file named `dunlin-demo.blyx`.
2. Type `blyx-dunlin-demo` and select **Dunlin — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
0
1
2
1
```

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-dunlin)
