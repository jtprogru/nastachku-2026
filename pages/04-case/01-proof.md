---
routeAlias: proof
layout: two-cols-header
layoutClass: gap-x-12
---

<Kicker>04 · пруф</Kicker>

# «Диски не подключаются к VM»

::left::

<p class="text-xl mt-0">Два managed-кластера клиента, пять операций подряд. Первый подозреваемый — сторадж.</p>

<p class="text-2xl font-bold leading-snug text-link">Через MCP за минуты: сторадж исключён.</p>

::right::

<div class="proof-code">

```text
жертвы      5 подов, одна нода
стадия      FailedCreatePodSandBox
том         до attach не дошло
демон CNI   Running/Ready
```

</div>

<style>
.proof-code { --slidev-code-font-size: 1.05rem; --slidev-code-line-height: 2; }
</style>

<!--
9:45–10:30 · 45 с. Через MCP за минуты: одна нода, отказ до тома. Сторадж исключён. Экран построчно не читать.

У клиента два managed-кластера Kubernetes, и к их worker-VM не подключаются диски, пять операций подряд. В нашем стеке первый подозреваемый всегда сторадж.

Справа то, что было на руках через MCP за несколько минут. Все пять подов на одной ноде, и до подключения тома дело не доходит. Демон CNI при этом Running и Ready.

Сторадж исключён.

Переход: «Почему из этого следует именно такой диагноз».

Справка. Жертвы — поды hotplug-подключения томов (hp-volume), рестартов у демона CNI ноль. Текст ошибки из событий: Failed to open current namespace: Statfs "/proc/12/task/59/ns/net": no such file or directory.
-->
