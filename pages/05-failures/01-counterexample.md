---
routeAlias: counterexample
---

<Kicker>05 · контрпример</Kicker>

# Все тулы зелёные. Клиент трое суток без записи

<div class="grid grid-cols-2 gap-8 mt-10">

<Card kicker="что сказали тулы" class="text-center">
<div class="text-5xl font-bold my-4" style="color: var(--c-tip-text)">всё зелёное</div>
<div class="font-mono text-sm">tenant_summary · console_probe<br>linstor · drbd</div>
</Card>

<Card kicker="что было в serial console" tone="danger" class="text-center">
<div class="text-5xl font-bold my-4" style="color: var(--c-danger-text)">7 521 122</div>
<div class="font-mono text-sm">ошибки файловой системы</div>
</Card>

</div>

<p class="text-2xl font-bold text-link text-center mt-12">Тул проверяет «гость отвечает?», а не «гость работает?»</p>

<!--
12:20–13:15 · 55 с. Тул проверяет «гость отвечает?», а не «гость работает?». Тулы не перечислять.

После ребута ноды под обновление ядра у виртуалки клиента повредилась ext4, и корень ушёл в read-only. Гость отвечал на ping и SSH, показывал login и не мог записать ни байта.

Все тулы зелёные. А в serial console семь с половиной миллионов ошибок файловой системы.

Три дня и шесть часов. Нашёл клиент: «это уже четвёртый раз».

[пауза] Тул отвечает на вопрос «гость отвечает?», а не «гость работает?».

Переход: «Из таких историй складываются три режима отказа».

На вопросы. Реальный инцидент, есть постмортем, идентификаторы убраны. Первая ошибка ФС — 31.08, 00:48:53. Тулы: tenant_summary зелёный, hints пусто, console_probe говорит guest OS is alive, linstor_resource_list faulty 0, drbd status UpToDate и quorum yes. У нас в архиве это третий разбор на этой машине. Правду показал не MCP, а полный лог серийной консоли из пода и строки суперблока ext4: они переживают ребуты и датируют поломку. Починили за 33 минуты от начала разбора: снапшот тома, offline e2fsck с ноды, VM обратно, процедура была известна. В то же окно ребута заново стартовало около 102 VM, сколько из них сломалось молча, мы не знаем: инструмента для массовой проверки нет.
-->
