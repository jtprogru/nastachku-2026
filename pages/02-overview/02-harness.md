---
routeAlias: harness
---

<Kicker>02 · харнес</Kicker>

# На чём собран MCP

<div class="harness grid grid-cols-[1fr_auto_1fr_auto_1fr_auto_1fr] items-center gap-3 mt-10 text-center">

<Card>
<div class="flex justify-center gap-3 text-5xl"><simple-icons-claude /><simple-icons-openai /></div>
<div class="harness__name">Клиент</div>
<div class="font-mono text-xs whitespace-nowrap">Claude Code · Codex</div>
</Card>

<span class="text-3xl text-muted">→</span>

<Card>
<div class="flex justify-center text-5xl"><simple-icons-go /></div>
<div class="harness__name">sre-mcp-bridge</div>
<div class="font-mono text-xs">stdio → mTLS</div>
</Card>

<span class="text-3xl text-muted">→</span>

<Card tone="accent">
<div class="flex justify-center text-5xl"><simple-icons-python /></div>
<div class="harness__name">sre-mcp</div>
<div class="font-mono text-xs">Python · 51 тул</div>
</Card>

<span class="text-3xl text-muted">→</span>

<div class="flex flex-col gap-3">
<Card>
<div class="flex justify-center gap-3 text-3xl"><simple-icons-postgresql /><simple-icons-ollama /></div>
<div class="harness__name">База знаний</div>
</Card>
<Card>
<div class="flex justify-center gap-3 text-3xl"><simple-icons-prometheus /><simple-icons-grafana /></div>
<div class="harness__name">Аудит и метрики</div>
</Card>
</div>

</div>

<p class="text-3xl font-bold text-link text-center mt-12">Вся политика живёт на сервере</p>

<style>
.harness__name { margin-top: 0.6rem; font-size: 1.15em; font-weight: 700; color: var(--fg); }
</style>

<!--
4:25–4:55 · 30 с. Вся политика живёт на сервере, модель и клиент заменяемы. Плитки не зачитывать, таблица компонентов — в справке ниже.

Клиент — Claude Code или Codex CLI со скиллом sre-ninja, между ним и сервером бридж на Go.

Сам sre-mcp на Python: пятьдесят один тул, тридцать один из них только чтение, остальные двадцать — процедуры с изменениями, про них в части о правах.

Главное: вся политика живёт на сервере. Модель и клиента можно поменять, правила доступа останутся.

Переход: «Одной картинкой это выглядит так».

Обязательно: фразу про двадцать тулов с изменениями не выкидывать. Она заранее отвечает на самый острый вопрос из зала.

Справка, бывшая таблица. Клиент: skill sre-ninja — сначала поиск в базе, потом L0, dry-run до любой мутации. sre-mcp-bridge на Go: stdio ↔ streamable HTTP по mTLS, JWT получает сам. sre-mcp на Python и FastMCP: 51 тул — 31 L0, 12 L1, 8 L2, обёртки над kubectl, linstor и drbdsetup, в ответ сводка. База знаний: Postgres + pgvector, постмортемы и раннбуки, гибридный поиск kb_search, эмбеддинги в Ollama. Аудит и метрики: JSONL с HMAC-цепочкой до выполнения, Prometheus, Grafana, OTel в планах.

На вопросы. Зачем бридж: Claude Code, Codex CLI и Claude Desktop не умеют mTLS с клиентским сертификатом. Почему не готовый вендорский AI SRE: нужны свои тулы к своей инфре — LINSTOR, DRBD, kube-ovn, такого из коробки нет.
-->
