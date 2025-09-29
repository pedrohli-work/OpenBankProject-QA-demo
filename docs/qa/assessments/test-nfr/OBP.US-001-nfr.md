# OBP.US-001-nfr.md
id: US-001
epic: OBP
title: "Autenticar via Direct Login e validar users/current"
criteria:
  performance:
    target: "Login e users/current ≤ 500ms p95"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Sem segredos em logs, tokens válidos ≤ TTL"
    current: "Não testado"
    status: "Pending"
  reliability:
    target: "Retries configurados para 5xx, 99% sucesso"
    current: "Não testado"
    status: "Pending"
  observability:
    target: "Logs mascarados; métricas de falhas registradas"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "Pending"
  blockers:
    - "Falta teste de logs mascarados"
    - "Falta teste de retries/backoff"
