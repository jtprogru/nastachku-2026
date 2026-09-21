<script setup lang="ts">
import Link from '@slidev/client/builtin/Link.vue'
import { computed, useId } from 'vue'

// Схема «все стрелки — read, одна пунктирная — propose».
//
// Источники слева сходятся в шину и одной сплошной стрелкой входят в
// ассистента; от ассистента к человеку идёт единственная пунктирная стрелка.
// Источник с `to` — ссылка на слайд (drill-down), рамка у него пунктиром.
//
// Геометрия шины считается от высоты строки источника: ROW и GAP ниже должны
// совпадать с высотой и зазором .arch__source в стилях.
type Source = string | { label: string, to: string | number }

const props = withDefaults(defineProps<{
  sources: Source[]
  agent?: string
  agentNote?: string
  human?: string
  humanNote?: string
  propose?: string
}>(), {
  agent: 'ИИ-ассистент',
  agentNote: 'MCP client · dry-run',
  human: 'Инженер',
  humanNote: 'apply · только человек',
  propose: 'propose',
})

const ROW = 34
const GAP = 8
const BUS_X = 36
const BUS_W = 96

const items = computed(() => props.sources.map(s => typeof s === 'string' ? { label: s, to: undefined } : s))
const height = computed(() => items.value.length * ROW + (items.value.length - 1) * GAP)
const rows = computed(() => items.value.map((_, i) => ROW / 2 + i * (ROW + GAP)))

const id = useId()
const readArrow = `arch-read-${id}`
const proposeArrow = `arch-propose-${id}`
</script>

<template>
  <div class="arch flex items-center justify-center">
    <div class="arch__sources flex flex-col" :style="{ gap: `${GAP}px` }">
      <template v-for="src in items" :key="src.label">
        <Link v-if="src.to !== undefined" :to="src.to" class="arch__source is-link">
          <span>{{ src.label }}</span>
          <span class="arch__read font-mono text-xs font-bold">read</span>
        </Link>
        <div v-else class="arch__source">
          <span>{{ src.label }}</span>
          <span class="arch__read font-mono text-xs font-bold">read</span>
        </div>
      </template>
    </div>

    <svg
      class="arch__bus shrink-0"
      :width="BUS_W"
      :height="height"
      :viewBox="`0 0 ${BUS_W} ${height}`"
      aria-hidden="true"
    >
      <defs>
        <marker :id="readArrow" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto">
          <path d="M0,0 L10,5 L0,10 z" class="arch__head-read" />
        </marker>
      </defs>
      <path v-for="y in rows" :key="y" :d="`M0,${y} H${BUS_X}`" class="arch__line-read" />
      <path :d="`M${BUS_X},${rows[0]} V${rows[rows.length - 1]}`" class="arch__line-read" />
      <path :d="`M${BUS_X},${height / 2} H${BUS_W - 2}`" class="arch__line-read" :marker-end="`url(#${readArrow})`" />
    </svg>

    <div class="arch__node arch__node--agent">
      <div class="arch__node-title">
        {{ props.agent }}
      </div>
      <div class="arch__node-note font-mono text-xs">
        {{ props.agentNote }}
      </div>
    </div>

    <div class="arch__propose shrink-0 flex flex-col items-center">
      <span class="arch__propose-label font-mono text-xs">{{ props.propose }}</span>
      <svg width="140" height="16" viewBox="0 0 140 16" aria-hidden="true">
        <defs>
          <marker :id="proposeArrow" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto">
            <path d="M0,0 L10,5 L0,10 z" class="arch__head-propose" />
          </marker>
        </defs>
        <path d="M8,8 H130" class="arch__line-propose" :marker-end="`url(#${proposeArrow})`" />
      </svg>
    </div>

    <div class="arch__node arch__node--human">
      <div class="arch__node-title">
        {{ props.human }}
      </div>
      <div class="arch__node-note font-mono text-xs">
        {{ props.humanNote }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.arch {
  --read: var(--accent-700);
}

html.dark .arch {
  --read: var(--accent-300);
}

.arch__sources {
  width: 17rem;
}

.arch__source {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 34px;
  padding: 0 0.9rem;
  border: 1px solid var(--border);
  border-radius: 8px;
  background: var(--bg-elev);
  color: var(--fg);
  font-size: 0.95em;
}

/* Тема красит <a> цветом ссылки с пунктиром снизу — здесь ссылка выглядит
   как источник, а кликабельность выдаёт пунктирная акцентная рамка. */
.arch__source.is-link {
  color: var(--fg);
  border: 1px dashed var(--accent-400);
  transition: background 0.15s ease;
}

.arch__source.is-link:hover {
  background: color-mix(in srgb, var(--accent-400) 10%, var(--bg-elev));
}

.arch__read {
  color: var(--read);
}

.arch__line-read {
  fill: none;
  stroke: var(--read);
  stroke-width: 2;
}

.arch__head-read {
  fill: var(--read);
}

.arch__node {
  padding: 1.5rem 1.25rem;
  border-radius: 10px;
  border: 1px solid var(--border);
  background: var(--bg-elev);
  text-align: center;
}

.arch__node--agent {
  width: 15rem;
  border-color: var(--accent-400);
  background: color-mix(in srgb, var(--accent-400) 7%, var(--bg-elev));
}

.arch__node--agent .arch__node-title {
  color: var(--read);
}

.arch__node--human {
  width: 13rem;
  border-color: var(--fg-muted);
}

.arch__node-title {
  font-size: 1.3em;
  font-weight: 700;
  line-height: 1.3;
  color: var(--fg);
}

.arch__node-note {
  margin-top: 0.4rem;
  color: var(--fg-muted);
}

.arch__propose {
  width: 9.5rem;
  gap: 0.2rem;
}

.arch__propose-label {
  color: var(--fg-muted);
}

.arch__line-propose {
  fill: none;
  stroke: var(--fg-muted);
  stroke-width: 2;
  stroke-dasharray: 7 6;
  animation: arch-march 1.2s linear infinite;
}

.arch__head-propose {
  fill: var(--fg-muted);
}

@keyframes arch-march {
  to {
    stroke-dashoffset: -13;
  }
}

@media (prefers-reduced-motion: reduce) {
  .arch__line-propose {
    animation: none;
  }
}
</style>
