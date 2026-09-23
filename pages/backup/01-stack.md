---
routeAlias: backup-stack
---

<Kicker>backup · стек</Kicker>

# Стек и харнес — если спросят

| слой | чем закрыт |
| --- | --- |
| **Кластеры** | Два Kubernetes, KubeVirt под VM клиентов, CNPG под managed PostgreSQL |
| **Хранилка** | Ceph; LINSTOR/DRBD под диски виртуалок |
| **Сеть** | kube-ovn, тенантские VPC и NAT-шлюзы |
| **Телеметрия** | VictoriaMetrics, Grafana, VictoriaTraces; курс на единый OTLP |
| **Инциденты** | OneUptime; раннбуки и постмортемы в Postgres + pgvector с эмбеддингами через Ollama |
| **MCP** | sre-mcp: Python, FastMCP, systemd-юнит за Caddy с mTLS + JWT; sre-mcp-bridge на Go для Claude Code и Codex CLI |

<Link to="questions" class="font-mono text-xs">← вернуться к вопросам</Link>

<style>
/* плотный слайд: основной текст мельче, заголовок остаётся в размере темы */
.slidev-layout { font-size: 0.95rem; }
.slidev-layout td, .slidev-layout th { padding-top: 0.45rem; padding-bottom: 0.45rem; }
</style>

<!--
Бэкап, скрыт из показа и экспорта через `hide: true` в slides.md. Если вернуть, встанет после «Вопросов»: стрелкой вперёд туда, ссылкой внизу обратно.

Пока скрыт, отвечать голосом. На вопрос про стек: два кластера Kubernetes, KubeVirt под VM клиентов, CNPG под managed PostgreSQL. Хранилка — Ceph и LINSTOR/DRBD под диски виртуалок, сеть — kube-ovn. Телеметрия — VictoriaMetrics, Grafana и VictoriaTraces. sre-mcp на Python и FastMCP за Caddy с mTLS и JWT, бридж на Go для Claude Code и Codex CLI.
-->
