---
theme: bear
layout: cover
mascot: true
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

<!-- ширина ограничена, чтобы заголовок не заезжал на маскота в правом нижнем углу -->
<div class="max-w-2xl">

# SRE MCP

<p class="!text-4xl !leading-tight !mt-0" style="color: var(--fg)">Как пустить ИИ в инцидент<br>и не отдать ему прод</p>

<p class="text-xl text-muted">Read-only по умолчанию, человек на кнопке —<br>и три места, где эта схема ломается</p>

<br>

#### [Мишка на сервере](https://t.me/jtprogru_channel) | [Михаил Савин](https://savinmi.ru) | Head of SRE, [h3llo cloud](https://h3llo.cloud) | 2026

</div>

<!--
35 минут про то, как мы пустили ИИ-ассистента в инцидент-менеджмент облачного провайдера и почему у него до сих пор нет прав на запись. Сразу дисклеймер — следующий слайд.
-->

---
# ── 00 · вступление ──
src: ./pages/00/speaker.md
---

---
src: ./pages/00/about.md
---

---
src: ./pages/00/promise.md
---

---
src: ./pages/00/contour.md
---

---
# ── 01 · Арифметика MTTR ──
src: ./pages/01/section.md
---

---
src: ./pages/01/scene.md
---

---
src: ./pages/01/mttr.md
---

---
src: ./pages/01/thesis.md
---

---
src: ./pages/01/replit.md
---

---
src: ./pages/01/research.md
---

---
# ── 02 · Что это такое ──
src: ./pages/02/section.md
---

---
src: ./pages/02/mcp60.md
---

---
src: ./pages/02/harness.md
---

---
src: ./pages/02/arch.md
---

---
# drill-down по клику на «База раннбуков» со схемы
src: ./pages/02/context-layer.md
---

---
src: ./pages/02/contract.md
---

---
# ── 03 · Права ──
src: ./pages/03/section.md
---

---
src: ./pages/03/thesis.md
---

---
src: ./pages/03/gates.md
---

---
src: ./pages/03/gate-1.md
---

---
src: ./pages/03/gate-2-3.md
---

---
src: ./pages/03/gate-4.md
---

---
src: ./pages/03/gate-5.md
---

---
src: ./pages/03/rbac.md
---

---
# ── 04 · Разбор ──
src: ./pages/04/section.md
---

---
src: ./pages/04/proof.md
---

---
src: ./pages/04/chain.md
---

---
src: ./pages/04/human.md
---

---
# ── 05 · Где ломается ──
src: ./pages/05/section.md
---

---
src: ./pages/05/counter.md
---

---
src: ./pages/05/fail-new.md
---

---
src: ./pages/05/fail-correlation.md
---

---
src: ./pages/05/fail-complacency.md
---

---
src: ./pages/05/long-incidents.md
---

---
# ── 06 · Цифры и старт ──
src: ./pages/06/section.md
---

---
src: ./pages/06/metric.md
---

---
# опциональный: режется первым, если не укладываюсь по времени
src: ./pages/06/audit-start.md
hide: false
---

---
src: ./pages/06/anti-pitch.md
---

---
src: ./pages/06/pilot.md
---

---
# ── 07 · финал ──
src: ./pages/07/takeaways.md
---

---
src: ./pages/07/materials.md
---

---
src: ./pages/07/questions.md
---

---
# ── бэкапы: скрыты из показа и экспорта, чтобы вернуть — убрать hide ──
src: ./pages/backup/stack.md
hide: true
---

---
src: ./pages/backup/cost.md
hide: true
---
