---
routeAlias: harness
---

<Kicker>02 · харнес</Kicker>

# На чём собран MCP

| компонент | зачем он здесь |
| --- | --- |
| **Claude Code / Codex CLI** | Клиент со skill sre-ninja: сначала поиск в базе, потом L0, dry-run до любой мутации. |
| **sre-mcp-bridge** · Go | stdio ↔ streamable HTTP по mTLS: клиенты не умеют клиентский сертификат. JWT получает сам. |
| **sre-mcp** · Python, FastMCP | 51 тул: 31 L0, 12 L1, 8 L2. Обёртки над `kubectl`, `linstor`, `drbdsetup`, в ответ — сводка. |
| **Postgres + pgvector** | База знаний: постмортемы и раннбуки, гибридный поиск `kb_search`, эмбеддинги в Ollama. |
| **Аудит и метрики** | JSONL с HMAC-цепочкой до выполнения, Prometheus, Grafana. OTel — в планах. |

> *Важен принцип: вся политика живёт на сервере. Клиента и модель можно поменять, правила доступа от этого не меняются.*

<style>
/* плотный слайд: основной текст мельче, заголовок остаётся в размере темы */
.slidev-layout { font-size: 0.9rem; }
.slidev-layout td, .slidev-layout th { padding-top: 0.45rem; padding-bottom: 0.45rem; }
</style>

<!--
Будут вопросы, зачем бридж: Claude Code, Codex CLI и Claude Desktop не умеют mTLS с клиентским сертификатом. И почему не готовый вендорский AI SRE: нужны свои тулы к своей инфре — LINSTOR, DRBD, kube-ovn, такого из коробки нет.
-->
