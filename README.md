<img src="assets/logo.png" width="112" height="112" alt="A rufous dunlin with a dark belly leans down to inspect the ground.">

# Dunlin

Audit a table export for duplicate parents and orphaned child rows. This Blyx workflow framework is part of the databases and migrations collection.

A child reference can look valid while the parent key is duplicated. Check uniqueness and referential integrity before a bulk import. [PostgreSQL, unique and foreign key constraints](https://www.postgresql.org/docs/current/ddl-constraints.html)

## Editor extension

Install **RahulChaube.blyx-dunlin** to run the worked example and use the framework’s function completions in a Blyx file. Open an empty `.blyx` file, enter `blyx-dunlin-demo`, then choose **Blyx: Run File**. [Editor downloads](https://www.blyx-lang.space/packages/dunlin#editor) · [Download the extension](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-dunlin-0.1.0.vsix) · [Starter with framework source](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-dunlin-starter-0.1.0.zip)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-dunlin.git
cd blyx-dunlin
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-dunlin) · [Package page](https://www.blyx-lang.space/packages/dunlin) · [Handbook](https://doc.blyx-lang.space/guide/dunlin)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-dunlin.git vendor/dunlin
```

```blyx
use vendor::dunlin::dunlin;

fn main() {
    let parents = [1, 1, 3];
    let children = [1, 2, 2];
    let result = dunlin_check(parents, children);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
0
1
2
1
```

## API

`dunlin_check(parents, children)`

Returns [load acceptable, duplicate parent rows, orphan child rows, first orphan row]. This local check complements database-enforced constraints. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| parents | Vector of values, each a exact signed integer |
| children | Vector of values, each a exact signed integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- "1,1,3" "1,2,2"
```

## Libraries

- [KeyDuplicates](https://github.com/Rahulchaube1/blyx-keyduplicates/tree/v0.1.0) — Find repeated primary-key occurrences in an offline table export.
- [ForeignMiss](https://github.com/Rahulchaube1/blyx-foreignmiss/tree/v0.1.0) — Count child rows referencing absent numeric parent keys.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-dunlin/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The [artwork notice](assets/NOTICE.txt) records credits for earlier editions.

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
