# Dravyn

![Dravyn Dragon Emblem](docs/assets/dravyn-dragon.png)

Dravyn is an independent general-purpose programming language shaped around calm, readable source code and a strong systems-language identity. Its source extension is `.dv`, its package tool is `dvpkg`, its manifest file is `dravyn.pkg`, and its command line entry point is `dvc`.

This repository is intentionally pure Dravyn source at this stage. The language, standard library, bootstrap design, examples, package manifests, tooling contracts, and self-hosting compiler plan are all written as `.dv` files so the project identity stays inside the language itself from the beginning.

## Language Identity

- Name: `Dravyn`
- Meaning: a distinct name for the Dravyn language ecosystem
- Brand mark: `dragon emblem`
- Source extension: `.dv`
- Package manager: `dvpkg`
- Package file: `dravyn.pkg`
- CLI target: `dvc`

## Core Syntax

```dravyn
set app = "Dravyn"

task greet(user: Text) {
  say("Ayubowan " + user)
}

task divide(a: Num, b: Num) -> Outcome<Num> {
  check b == 0 {
    give fail("Cannot divide by zero")
  }

  give pass(a / b)
}

set answer = divide(10, 2)?
say(answer)
```

## Reserved Words

- `set`
- `task`
- `check`
- `elseway`
- `loopwhile`
- `give`
- `pass`
- `fail`
- `say`

## Built-in Types

- `Text`
- `Num`
- `Truth`
- `Outcome<T>`
- `Pack<T>`
- `Shape`

## Data Forms

- Text values: `"tea"`
- Truth values: `yes`, `no`
- Pack values: `pack[1, 2, 3]`
- Shape values: `shape[name: "Dravyn", domain: "systems"]`

## MVP Surface

- variables with `set`
- tasks with typed parameters
- `give` returns
- `check / elseway`
- `loopwhile`
- numbers, text, truth values
- arithmetic and comparison
- packs and shapes
- `Outcome`-based failure flow
- postfix `?` outcome unwrap
- `say` output
- no null value by default

## Dravyn-Unique Direction

- `Ward` capabilities for explicit access to file, network, device, and process effects
- `Journey` pipelines for named multi-step work with built-in failure tracing
- `Tide` lanes for deterministic concurrency without hidden shared-state chaos
- `Outcome` as the normal fallible path instead of exception-heavy control flow
- shaped records and packs kept readable for backend, edge, and CLI systems

## General-Purpose Aim

- one language for CLI tools, APIs, backend services, automation, device software, and language tooling
- fast toolchain habits inspired by Go and C# without copying their surface
- evented and embedded runtime ideas inspired by JavaScript without inheriting JavaScript's loose semantics
- large-codebase structure and library discipline inspired by Java and C#
- safety, explicit effects, and predictable performance inspired by Rust while keeping Dravyn syntax distinctly Dravyn

## Learned Lessons, Not Copied Syntax

- from Java: scale, package discipline, long-lived codebase structure
- from JavaScript: scripting reach, runtime embedding, event-driven workflows
- from Go: simple commands, fast builds, deployable tooling, direct concurrency thinking
- from Rust: safety-first design, explicit resources, strong compiler guidance
- from C#: productive tooling, modern async workflows, broad application reach

## Industry Foundation

- clear bootstrap and self-hosting split
- CLI, diagnostics, formatter, linter, registry, and project-template contracts
- core modules for backend, filesystem, HTTP, process control, async work, testing, time, JSON-like shaping, and device workflows
- example apps for hello world, math, API, CLI, and device automation
- local package samples and starter templates
- language-native test specs for compiler, VM, CLI, formatter, linter, templates, and dvpkg

## Project Layout

```text
bootstrap/
  compiler/
  runtime/
src/
  lexer.dv
  parser.dv
  ast.dv
  checker.dv
  diagnostics.dv
  interpreter.dv
  compiler.dv
  vm.dv
  cli.dv
  dvpkg.dv
  project.dv
  formatter.dv
  linter.dv
  registry.dv
  ward.dv
  journey.dv
  tide.dv
core/
  async.dv
  io.dv
  text.dv
  math.dv
  result.dv
  collections.dv
  fs.dv
  http.dv
  net.dv
  process.dv
  testing.dv
  time.dv
  data.dv
  ward.dv
  journey.dv
  tide.dv
examples/
  hello.dv
  math.dv
  api.dv
  device.dv
  cli.dv
  workflow.dv
  fleet.dv
packages/
templates/
docs/
tests/
dravyn.pkg
README.md
```

## Repository Intent

- `bootstrap/` holds the first compiler and runtime design in Dravyn form.
- `src/` is the self-hosting compiler track.
- `core/` is the future standard library.
- `examples/` shows CLI, backend, math, and device-oriented programs.
- `packages/` contains local dvpkg package samples.
- `templates/` stores starter projects for `dvc new`.
- `tests/` stores language-native specification cases.

## CLI Target

These commands are the contract Dravyn is aiming at:

- `dvc new project_name`
- `dvc run main.dv`
- `dvc check main.dv`
- `dvc build main.dv`
- `dvpkg init`
- `dvpkg add package_name`
- `dvpkg install`

## Documentation

- [docs/overview.md](/Users/lahiruudayakumara/sera/docs/overview.md)
- [docs/syntax.md](/Users/lahiruudayakumara/sera/docs/syntax.md)
- [docs/dvpkg.md](/Users/lahiruudayakumara/sera/docs/dvpkg.md)
- [docs/toolchain.md](/Users/lahiruudayakumara/sera/docs/toolchain.md)
- [docs/spec.md](/Users/lahiruudayakumara/sera/docs/spec.md)
- [docs/language-design.md](/Users/lahiruudayakumara/sera/docs/language-design.md)
- [docs/system-design.md](/Users/lahiruudayakumara/sera/docs/system-design.md)
- [docs/industry.md](/Users/lahiruudayakumara/sera/docs/industry.md)
- [docs/design.md](/Users/lahiruudayakumara/sera/docs/design.md)
- [docs/general-purpose.md](/Users/lahiruudayakumara/sera/docs/general-purpose.md)
- [docs/distinctives.md](/Users/lahiruudayakumara/sera/docs/distinctives.md)
- [docs/roadmap.md](/Users/lahiruudayakumara/sera/docs/roadmap.md)

## Current Stage

Dravyn now has a pure `.dv` source tree, language design, compiler layout, tooling contracts, examples, templates, manifests, and test corpus. The next execution milestone is turning the bootstrap compiler plan under `bootstrap/` into a runnable first compiler without compromising the language identity.
