---
theme: bear
layout: cover
routeAlias: cover
title: 'SRE MCP'
info: |
  ## SRE MCP: как пустить ИИ в инцидент и не отдать ему прод

  Read-only по умолчанию, человек на кнопке — и три места, где эта схема ломается.

  Михаил Савин, Head of SRE в h3llo cloud.

  Сделано с помощью [Sli.dev](https://sli.dev)
author: Михаил Савин
keywords: SRE,MCP,инцидент-менеджмент,observability
drawings:
  persist: false
transition: slide-left
mdc: true
---

<StachkaLogo class="absolute top-12 left-16" />

<!-- маскот свой, а не из лейаута (`mascot: true` даёт 200px): место то же, но чуть меньше, чтобы не спорить с логотипом -->
<Mascot :size="170" class="absolute bottom-10 right-12 pointer-events-none" />

<!-- ширина ограничена, чтобы заголовок не заезжал на маскота в правом нижнем углу -->
<div class="max-w-2xl">

# SRE MCP

<p class="!text-4xl !leading-tight !mt-0" style="color: var(--fg)">Как пустить ИИ в инцидент<br>и не отдать ему прод</p>

<br>

#### [Михаил Савин](https://savinmi.ru) · Head of SRE, [h3llo cloud](https://h3llo.cloud)

</div>

<!--
0:00–0:15 · 15 с. Слот 30 минут: 25:25 доклад, остальное вопросы. Одна фраза: о чём доклад и почему у ИИ нет записи.

Привет. Следующие двадцать пять минут про то, как мы пустили ИИ-ассистента в инцидент-менеджмент облачного провайдера. И почему у него до сих пор нет прав на запись.

На записи без ведущего сначала представиться: «Меня зовут Михаил Савин, я Head of SRE в h3llo cloud».

Переход: «Пару слов о себе: организаторы попросили».
-->

---
# ── 00 · вступление ──
src: ./pages/00-intro/01-speaker.md
---

---
src: ./pages/00-intro/02-disclaimer.md
---

---
src: ./pages/00-intro/03-promise.md
---

---
src: ./pages/00-intro/04-contour.md
---

---
# ── 01 · Арифметика MTTR ──
src: ./pages/01-mttr/00-section.md
---

---
src: ./pages/01-mttr/01-scene.md
---

---
src: ./pages/01-mttr/02-mttr.md
---

---
src: ./pages/01-mttr/03-thesis.md
---

---
src: ./pages/01-mttr/04-replit.md
---

---
src: ./pages/01-mttr/05-research.md
hide: true
---

---
# ── 02 · Что это такое ──
src: ./pages/02-overview/00-section.md
---

---
src: ./pages/02-overview/01-mcp60.md
hide: true
---

---
src: ./pages/02-overview/02-harness.md
---

---
src: ./pages/02-overview/03-arch.md
---

---
# drill-down по клику на «База раннбуков» со схемы
src: ./pages/02-overview/04-context-layer.md
---

---
src: ./pages/02-overview/05-contract.md
---

---
# ── 03 · Права ──
src: ./pages/03-permissions/00-section.md
---

---
src: ./pages/03-permissions/01-thesis.md
---

---
src: ./pages/03-permissions/02-gates.md
---

---
src: ./pages/03-permissions/03-gate-1.md
---

---
src: ./pages/03-permissions/04-gate-2-3.md
---

---
src: ./pages/03-permissions/05-gate-4.md
---

---
src: ./pages/03-permissions/06-gate-5.md
---

---
src: ./pages/03-permissions/07-rbac.md
---

---
# ── 04 · Разбор ──
src: ./pages/04-case/00-section.md
---

---
src: ./pages/04-case/01-proof.md
---

---
src: ./pages/04-case/02-chain.md
---

---
src: ./pages/04-case/03-human.md
---

---
# ── 05 · Где ломается ──
src: ./pages/05-failures/00-section.md
---

---
src: ./pages/05-failures/01-counterexample.md
---

---
src: ./pages/05-failures/02-fail-new.md
---

---
src: ./pages/05-failures/03-fail-correlation.md
---

---
src: ./pages/05-failures/04-fail-complacency.md
---

---
src: ./pages/05-failures/05-long-incidents.md
---

---
# ── 06 · Цифры и старт ──
src: ./pages/06-start/00-section.md
---

---
src: ./pages/06-start/01-metric.md
---

---
src: ./pages/06-start/02-audit-start.md
hide: true
---

---
src: ./pages/06-start/03-anti-pitch.md
---

---
src: ./pages/06-start/04-pilot.md
---

---
# ── 07 · финал ──
src: ./pages/07-outro/01-takeaways.md
---

---
src: ./pages/07-outro/02-materials.md
---

---
src: ./pages/07-outro/03-qr.md
---

---
src: ./pages/07-outro/04-questions.md
---

---
# ── бэкапы: скрыты из показа и экспорта, чтобы вернуть — убрать hide ──
src: ./pages/backup/01-stack.md
hide: true
---

---
src: ./pages/backup/02-cost.md
hide: true
---
