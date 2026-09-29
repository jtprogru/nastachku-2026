---
routeAlias: counterexample
layout: two-cols-header
layoutClass: gap-x-12
---

<Kicker>05 · контрпример</Kicker>

# Все тулы зелёные. Клиент трое суток без записи

::left::

<p class="text-xl mt-0">После ребута ноды у VM сломалась ext4, корень ушёл в read-only. Ping и SSH при этом отвечали.</p>

<p class="text-xl font-bold leading-snug text-link">3 суток 6 часов.<br>Нашёл клиент: «четвёртый раз».</p>

<Card tone="danger" class="text-lg">

Тул проверяет «гость отвечает?», а не «гость работает?»

</Card>

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

<p class="text-xl font-bold leading-snug !my-0">7 521 122 ошибки ФС в serial console</p>

</Callout>

<!--
12:20–13:15 · 55 с. Тул проверяет «гость отвечает?», а не «гость работает?». Тулы справа не перечислять.

После ребута ноды под обновление ядра у виртуалки клиента повредилась ext4, и корень ушёл в read-only. Гость отвечал на ping и SSH, показывал login и не мог записать ни байта.

Все тулы зелёные. А в serial console семь с половиной миллионов ошибок файловой системы.

Три дня и шесть часов. Нашёл клиент: «это уже четвёртый раз».

[пауза] Тул отвечает на вопрос «гость отвечает?», а не «гость работает?».

Переход: «Из таких историй складываются три режима отказа».

На вопросы. Реальный инцидент, есть постмортем, идентификаторы убраны. Первая ошибка ФС — 31.08, 00:48:53. Тулы: tenant_summary зелёный, console_probe говорит guest OS is alive, LINSTOR faulty 0, DRBD UpToDate. У нас в архиве это третий разбор на этой машине. Правду показал не MCP, а полный лог серийной консоли из пода и строки суперблока ext4: они переживают ребуты и датируют поломку. Починили за 33 минуты от начала разбора: снапшот тома, offline e2fsck с ноды, VM обратно, процедура была известна. В то же окно ребута заново стартовало около 102 VM, сколько из них сломалось молча, мы не знаем: инструмента для массовой проверки нет.
-->
