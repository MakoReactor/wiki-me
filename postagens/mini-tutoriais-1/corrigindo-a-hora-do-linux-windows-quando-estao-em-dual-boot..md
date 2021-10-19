---
description: '- https://itsfoss.com/wrong-time-dual-boot/'
---

# Corrigindo a Hora do Linux-Windows quando estão em dual boot.

As vezes quando usamos algum Linux e Windows em dua boot, percebemos que os mesmos estão com horários diferentes. No caso um vai estar correto e o outro vai estar errado.

Para corrigir vamos usar esse comando no Linux.

```
$> timedatectl set-local-rtc 1
```

Tudo isso ocorre porque o windows acha que o horário do hardware (relógio da bios) é o horário local e o linux por sua vez entende o mesmo horário como sendo o UTC.

O comando feito acima faz o linux reconhecer o horário do reloógio do hardware como horário local, assim ele não faz o cálculo UTC.\
\
