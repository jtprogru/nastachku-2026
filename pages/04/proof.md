---
layout: two-cols-header
layoutClass: gap-x-12
---

<Kicker>04 · пруф</Kicker>

# «Диски не подключаются к VM»

::left::

<p class="text-lg mt-0">У клиента два managed-кластера Kubernetes, и к их worker-VM не подключаются диски: пять операций подряд. В нашем стеке первый подозреваемый — всегда сторадж.</p>

<p class="text-xl font-bold leading-snug text-link">Через MCP за минуты: все жертвы на одной ноде, отказ до подключения тома. Сторадж исключён.</p>

::right::

```text
что собрано через MCP

жертвы        5 подов hp-volume, одна нода
стадия        FailedCreatePodSandBox,
              до attach тома не доходит
ошибка        Failed to open current namespace:
              Statfs "/proc/12/task/59/ns/net":
              no such file or directory
демон CNI     Running/Ready, рестартов нет
сторадж       к зависшим подам не относится
```

<!--
Не читать экран построчно. Сказать: вот что было на руках через несколько минут, а теперь разберём, почему из этого следует диагноз.
-->
