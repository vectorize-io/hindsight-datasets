# supportbench

**Does a support agent use the product docs and each customer's history correctly?**

A support agent for a managed Nextcloud hosting service remembers each customer's past support chats
and can read the real Nextcloud 32 manuals. Customers ask questions that never say which source to
use: deciding that is the point.

- `Nextcloud_User_Manual_32.pdf`, `Nextcloud_Server_Administration_Manual_32.pdf`: the real
  manuals, 837 pages with screenshots, as published at docs.nextcloud.com/server/32/ (sha256 pinned
  in the scenario).
- `supportbench.json`: the scenario — 20 customers, 260 support chats (heavy on-topic noise,
  including confident wrong claims), 35 approved exception notes, and 114 questions with gold answers,
  traps (`must_not_claim`) and sources (manual page and section, chat or exception id).

Question groups:

| Category | Count | The answer needs |
| --- | --- | --- |
| `docs_only` | 26 | the manuals; the customer's chats don't touch the topic |
| `needs_both` | 26 | a fact from the customer's chats plus a rule from the manuals |
| `conflict` | 26 | the manuals, which contradict something said in a past chat |
| `exception` | 36 | the same question from two customers: one has an approved exception, the other gets the documented default |

The runner, judge and memory setups live in AMB (`src/memory_bench/dataset/supportbench.py`).

## License

- `supportbench.json`: MIT, © 2026 Vectorize, Inc.
- The two manuals: © Nextcloud GmbH and contributors, licensed
  [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/), redistributed unmodified from
  https://docs.nextcloud.com/server/32/ (source: https://github.com/nextcloud/documentation).
