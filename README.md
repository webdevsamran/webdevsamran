## Samran Asif — [@webdevsamran](https://github.com/webdevsamran)

I build verification tools: programs whose entire value is that you can trust
what they tell you. Four of them, all Python, all local-first, all Apache-2.0.

### Projects

| | What it does |
|---|---|
| **[api-verity-lab](https://github.com/webdevsamran/api-verity-lab)** | API contract governance. Spec diffing with stable change ids, direction-aware breaking-change rules, schema-driven testing, runtime drift detection, traffic replay and performance budgets — for OpenAPI, AsyncAPI, GraphQL and gRPC, through one normalized contract model. |
| **[devrepro-doctor](https://github.com/webdevsamran/devrepro-doctor)** | "Works on my machine", diagnosed. Read-only scans of developer machines and project toolchains, privacy-sanitized reproducibility snapshots, machine-to-machine diffs, and repair plans that never apply themselves above LOW risk. |
| **[tooltrace-bench](https://github.com/webdevsamran/tooltrace-bench)** | Vendor-neutral, reproducible benchmarking of AI agents on real tool-use tasks — coding, file operations, multi-step workflows, failure recovery — scored deterministically from execution traces rather than from the agent's own account of what it did. |
| **[local-ai-hardware-bench](https://github.com/webdevsamran/local-ai-hardware-bench)** | Vendor-neutral benchmarking of local AI runtimes across CPUs, GPUs, NPUs and edge accelerators. One load generator drives every backend, so two numbers differ only in what they measured. |

They share no code and no release cycle. Each is usable on its own.

### How I work on them

A rule the four have in common, and the thing I care most about: **anything a
README or a report claims has to be traceable to something the code actually
produced.**

That is easy to say and easy to drift away from, so it is enforced rather than
intended. Every example block in every README is captured from a real run by a
script that CI re-runs on each push and fails on drift. Counts of commands,
rules, pages and packs are derived from the code, not typed into prose. Status
tables are machine-checked: a row claiming a feature has to cite something that
exists on disk. Badges are checked too — a Python-version badge only passes if
CI actually runs that version.

The uncomfortable half of that rule is what it turns up. Applying it found a
README documenting a rule id no code emits, a benchmark's "real sample run"
whose numbers traced back to a frontend demo fixture, an SBOM listing unrelated
projects as dependencies, a CI step named for a validation it never performed,
and a shipped GitHub Action whose exit-code gate could never fire. All of them
are fixed, and each fix ships with the check that would have caught it.

I would rather a tool say **unknown** than guess.

### Contributing

All four take issues and pull requests. Each has `CONTRIBUTING.md`, a
`SECURITY.md` pointing at GitHub's private vulnerability reporting, a
`CODE_OF_CONDUCT.md` whose reporting address is one that works, and an
`AGENTS.md` for anyone — human or otherwise — who wants the constraints that
are correctness rather than style before touching the code.

That last set is more recent than it should be: two of the four Codes of
Conduct used to point at GitHub features that do not exist, and private
vulnerability reporting was documented in all four repositories and enabled in
none. Both are fixed, and both are now checked by a test.
