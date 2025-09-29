<pre>
id: US-007
epic: OBP
title: "Convidar usuários para um projeto"
criteria:
  performance:
    target: "Envio de convite ≤ 1s p95 (com email mock)"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Tokens de convite one-time; TTL ≤ 24h"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Reenvio idempotente; sem duplicidade de membros"
    current: "Não testado"
    status: "Pending"
  observability:
    target: "Eventos invited/accepted; razão de aceite"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Sem teste para convite expirado (AC4)"
</pre>
