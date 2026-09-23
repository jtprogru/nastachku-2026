---
routeAlias: counterexample
layout: two-cols-header
layoutClass: gap-x-12
---

<Kicker>05 · контрпример</Kicker>

# Все тулы зелёные. Клиент трое суток без записи

::left::

<p class="text-lg mt-0">После ребута ноды под обновление ядра у VM повредилась ext4, и корень ушёл в read-only. Гость отвечал на ping и SSH и показывал login, но не мог записать ни байта.</p>

<p class="text-xl font-bold leading-snug text-link">3 суток 6 часов.<br>Нашёл клиент: «четвёртый раз».</p>

::right::

<Callout type="note" title="Что сказали тулы">

<div class="grid grid-cols-[auto_1fr] gap-x-4 items-baseline leading-normal">
<span class="font-mono text-sm">tenant_summary</span><span>всё зелёное, hints пусто</span>
<span class="font-mono text-sm">console_probe</span><span>«guest OS is alive»</span>
<span class="font-mono text-sm">linstor_resource_list</span><span>faulty: 0</span>
<span class="font-mono text-sm">drbd status</span><span>UpToDate, quorum: yes</span>
</div>

</Callout>

<Callout type="danger" title="Что было на самом деле">

<p class="text-xl font-bold leading-snug !mb-0">7 521 122 ошибки ФС в serial console</p>
<p class="!mt-1">Первая ошибка: 31.08, 00:48:53.</p>

</Callout>

<Card tone="danger" class="mt-4">

Тул отвечает на вопрос «гость отвечает?», а не «гость работает?». Эту разницу не покрывает ни один индикатор.

</Card>

<style>
/* плотный слайд: основной текст мельче, заголовок остаётся в размере темы */
.slidev-layout { font-size: 0.92rem; }
</style>

<!--
Реальный инцидент, есть постмортем, идентификаторы убраны. Правду показал не MCP, а полный лог серийной консоли из пода и строки суперблока ext4 — они переживают ребуты и датируют поломку.

Починили за 33 минуты от начала разбора: снапшот тома, offline e2fsck с ноды, VM обратно. Процедура была известна, это третий разбор на одной и той же VM.

В то же окно ребута заново стартовало около 102 VM. Сколько из них сломалось молча, неизвестно: инструмента для массовой проверки нет.
-->
