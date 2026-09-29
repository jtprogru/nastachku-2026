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
0:00–0:10 · 10 с. План 18:20 при слоте 30 минут: на живых прогонах доклад идёт примерно в полтора раза дольше плана, отсюда запас. Название и сразу к крючку, представляться потом.

Привет. Доклад про то, как пустить ИИ в инцидент и не отдать ему прод. Начну с картинки, которую знает каждый дежурный.

На записи без ведущего сначала представиться: «Меня зовут Михаил Савин, я Head of SRE в h3llo cloud».
-->

---
# ── 00 · вступление ──
src: ./pages/00-intro/01-hook.md
---

---
src: ./pages/00-intro/02-speaker.md
---

---
src: ./pages/00-intro/03-disclaimer.md
hide: true
---

---
src: ./pages/00-intro/04-promise.md
---

---
src: ./pages/00-intro/05-contour.md
---

---
# ── 01 · Арифметика MTTR ──
src: ./pages/01-mttr/00-section.md
---

---
src: ./pages/01-mttr/01-mttr.md
---

---
src: ./pages/01-mttr/02-thesis.md
---

---
src: ./pages/01-mttr/03-replit.md
---

---
src: ./pages/01-mttr/04-research.md
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
src: ./pages/03-permissions/02-gate-1.md
---

---
src: ./pages/03-permissions/03-gate-2-3.md
---

---
src: ./pages/03-permissions/04-gate-4.md
---

---
src: ./pages/03-permissions/05-gate-5.md
---

---
src: ./pages/03-permissions/06-rbac.md
hide: true
---

---
src: ./pages/03-permissions/07-gates.md
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
src: ./pages/05-failures/01-fail-tool.md
---

---
src: ./pages/05-failures/02-fail-model.md
---

---
src: ./pages/05-failures/03-fail-complacency.md
---

---
src: ./pages/05-failures/04-long-incidents.md
hide: true
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
