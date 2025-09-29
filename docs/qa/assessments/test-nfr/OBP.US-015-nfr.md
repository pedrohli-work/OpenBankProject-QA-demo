# OBP.US-015-nfr.md
id: US-015
epic: OBP
title: "Pesquisar tarefas, projetos e usuários"
criteria:
  performance:
    target: "Latência p95 ≤ 300ms (índice quente) e p99 ≤ 600ms; paginação estável; throughput ≥ 200 qps por nó"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Enforcement de escopo por projeto/tenant e papel; sem vazamento entre projetos; rate limiting e WAF para consultas maliciosas"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Consistência eventual ≤ 5s pós-escrita; paginação com cursor/nextToken; proteção contra resultados fantasma em reindexação"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Métricas de latência (p50/p95/p99), acurácia/relevância amostral, taxa de erro 4xx/5xx, hits por índice; logs com trace-id e query-id (sem PII)"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Teste de vazamento em filtros compostos (AC2) ainda ausente"
    - "Sem validação de relevância com fuzzy/typo-boost (AC1)"
