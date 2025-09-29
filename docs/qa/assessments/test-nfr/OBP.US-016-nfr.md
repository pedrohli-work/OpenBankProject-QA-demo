# OBP.US-016-nfr.md
id: US-016
epic: OBP
title: "Gerar relatórios de progresso do projeto"
criteria:
  performance:
    target: "Geração p95 ≤ 2s para 1k tarefas; p99 ≤ 5s; stream de download inicia ≤ 1s; CSV gerado em streaming"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Autorização por papel/escopo; no CSV escapar fórmulas (=,+,-,@); PDF sem conteúdo ativo; URLs de download assinadas e com expiração"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Idempotência por request-id; cancelamento e retry com backoff; snapshot consistente do estado; limites de tamanho e paginação interna"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Métricas de geração (latências p50/p95/p99, taxa de erro, bytes/s); logs com trace-id e project-id; eventos report_generated/failed"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Falta cobertura para injeção CSV (P1)"
    - "Ausência de teste de consistência durante geração concorrente (P2)"
