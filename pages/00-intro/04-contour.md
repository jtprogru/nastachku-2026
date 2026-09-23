---
routeAlias: contour
---

<Kicker>00 · контур</Kicker>

# На чём это работает у нас

<div class="grid grid-cols-2 gap-4">
<Card title="Вычисления">Два кластера Kubernetes, KubeVirt для VM клиентов, CNPG для managed PostgreSQL</Card>
<Card title="Хранение и сеть">Ceph, LINSTOR/DRBD под диски виртуалок, kube-ovn для тенантских сетей</Card>
<Card title="Наблюдаемость">VictoriaMetrics и Grafana, курс на единый OTLP-стек, VictoriaTraces под трейсы</Card>
<Card title="Процесс">OneUptime как инцидент-трекер, self-hosted GitLab с реестром образов</Card>
</div>

<Card tone="accent" class="mt-6">

Масштаб важен для честности этого доклада: ранняя стадия, около десяти технических специалистов на всю компанию, один SRE. Это не история про то, как большая команда автоматизировала дежурство. Это история про то, как маленькая команда попыталась не утонуть.

</Card>

<!--
Не перечислять весь стек вслух. Главное — последний абзац: масштаб команды объясняет, почему схема именно такая.
-->
