# OBP.US-010-nfr.md
id: US-010
epic: OBP
title: "Atribuir tarefas a membros do time"
criteria:
  performance:
    target: "Atribuição p95 ≤ 300ms; notificação enviada ≤ 2s"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Bloqueio de atribuição a não-membros (403) 100% dos casos"
    current: "Não testado"
    status: "Pending"
  reliability:
    target: "Sem conflito em dupla atribuição (locks otimistas)"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Evento task_assigned + entrega de notificação metrificada"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Sem teste de notificação entregue (AC3)"
    - "Concorrência não coberta integralmente"
