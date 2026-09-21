
<Kicker>04 · пруф</Kicker>

# Цепочка вывода — то, что можно проверить

1. Пять подов hotplug-подключения дисков висят в `Pending`, и все на одной ноде.
   <span class="block font-mono text-xs text-muted -mt-1">источник: kube API</span>
2. `FailedCreatePodSandBox`: под не получает сеть, до подключения тома дело не доходит. Значит, не сторадж.
   <span class="block font-mono text-xs text-muted -mt-1">источник: kube events</span>
3. Демон CNI держит namespace уже мёртвого процесса. При этом он `Running/Ready` — пробы этого не видят.
   <span class="block font-mono text-xs text-muted -mt-1">источник: текст ошибки + статус пода</span>
4. Отказ локальный для ноды: лечится пересозданием пода демона CNI на ней.
   <span class="block font-mono text-xs text-muted -mt-1">источник: вывод</span>

<Card tone="accent" class="mt-4">

Ценность не в тексте ошибки, а в дискриминаторе: все жертвы на одной ноде и отказ раньше тома — значит, не сторадж. Там, где сторадж подозревают по умолчанию, это экономит время.

</Card>

<style>
/* плотный слайд: основной текст мельче, заголовок остаётся в размере темы */
.slidev-layout { font-size: 0.92rem; }
.slidev-layout li { line-height: 1.7; margin-bottom: 0.4rem; }
</style>

<!--
Подчеркнуть: инженер прочитал цепочку и мог не согласиться на любом шаге. Поэтому цепочка обязательна в контракте ответа.
-->
