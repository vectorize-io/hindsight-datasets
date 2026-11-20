# hindsight-datasets

Datasets built by the Hindsight team for [agent-memory-benchmark](https://github.com/vectorize-io/agent-memory-benchmark)
(AMB), which mounts this repo as a git submodule at `datasets/`. Each folder is one dataset with its
own README and license.

| Folder | What it tests | License |
| --- | --- | --- |
| [`sdebench/`](sdebench/) | Does a coding agent fix bugs right the first time when it remembers the project's past decisions? 61 bug-fix tasks on a real codebase. | MIT |
| [`supportbench/`](supportbench/) | Does a support agent use the product manuals and each customer's history correctly? Real Nextcloud 32 manuals plus per-customer support chats. | Scenario MIT, manuals CC BY 3.0 |
| [`broken-media/`](broken-media/) | Does a knowledge bank take odd, broken and huge files (damaged video, PDFs that crash the renderer, malformed Office files) without breaking? 26 files, one per problem found. Used by hindsight-system-evals, not AMB. | Per source: Apache-2.0, MIT, public domain (see its README) |

This repo was `vectorize-io/sde-bench`; old links redirect here and sde-bench now lives in `sdebench/`.
