# OBP.US-005-nfr.md
id: US-005
epic: OBP
title: "Visualizar dashboard inicial personalizado"
criteria:
  performance:
    target: "Render p95 ≤ 1.2s; agregadores p95 ≤ 600ms"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Enforcement de entitlements em todos os agregadores"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Degradação graciosa com 99% de sucesso em falhas parciais"
    current: "Não testado"
    status: "Pending"
  observability:
    target: "Métricas por widget; tracing de fan-out"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Falta teste de isolamento de dados (AC4)"
    - "Métricas e tracing ausentes"
