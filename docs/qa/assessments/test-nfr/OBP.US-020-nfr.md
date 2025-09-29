# OBP.US-020-nfr.md
id: US-020
epic: OBP
title: "Exportar dados do projeto (CSV, PDF)"
criteria:
  performance:
    target: "Geração p95 ≤ 2s (até 1k registros) e p99 ≤ 5s; início do stream ≤ 1s; CSV produzido em streaming/chunked"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Autorização por papel/escopo; CSV com escape de fórmulas; PDF sem conteúdo ativo; URLs de download assinadas com expiração; rate limiting por usuário/projeto"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Snapshot consistente do estado; idempotência por request-id; retry com backoff; limites de tamanho e paginação interna; detecção de arquivo corrompido"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Métricas de geração (latência p50/p95/p99, throughput, taxa de erro); logs com trace-id e project-id; eventos export_started/export_succeeded/export_failed"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Faltam testes para proteção contra injeção de fórmulas em CSV (AC1)"
    - "Ausência de validação de snapshot consistente sob concorrência (AC3)"
