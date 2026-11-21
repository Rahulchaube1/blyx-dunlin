# Blyx Dunlin

Audit a table export for duplicate parents and orphaned child rows.

This extension includes the Blyx Dunlin 0.1.0 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Run in the editor

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

## Use Dunlin in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/dunlin`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-dunlin-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-dunlin-starter-0.1.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/dunlin) · [Framework source](https://github.com/Rahulchaube1/blyx-dunlin/tree/19220f4076dab1f086a2252d862869843a8bbdc2) · [Report an issue](https://github.com/Rahulchaube1/blyx-dunlin/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
