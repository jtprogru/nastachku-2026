---
routeAlias: contour
---

<Kicker>00 · контур</Kicker>

# На чём это работает у нас

<div class="grid grid-cols-2 gap-4 text-xl">
<Card v-click title="Вычисления">Два кластера Kubernetes, KubeVirt, CNPG</Card>
<Card v-click title="Хранение и сеть">Ceph, LINSTOR/DRBD, kube-ovn</Card>
<Card v-click title="Наблюдаемость">VictoriaMetrics, Grafana, VictoriaTraces</Card>
<Card v-click title="Процесс">OneUptime, self-hosted GitLab</Card>
</div>

<p v-click class="text-3xl font-bold text-link mt-10">~10 технических специалистов · 1 SRE</p>

<!--
1:45–2:05 · 20 с. Стек не читать, карточки просто открыть. Главное — масштаб: один SRE объясняет, почему схема именно такая.

[click] Вычисления, [click] хранение и сеть, [click] наблюдаемость, [click] процесс. Стек читать не буду. Запомните KubeVirt, LINSTOR и kube-ovn, они ещё всплывут.

[click] Главное здесь масштаб: около десяти технических специалистов на всю компанию и один SRE. Это история про маленькую команду, которая пытается не утонуть.

Переход: «Теперь арифметика».

Справка, если спросят про стек: KubeVirt под VM клиентов, CNPG под managed PostgreSQL, LINSTOR/DRBD под диски виртуалок, kube-ovn под тенантские сети. Наблюдаемость идёт к единому OTLP-стеку. OneUptime — инцидент-трекер, в GitLab реестр образов.
-->
