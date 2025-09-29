<pre>
id: US-019
epic: OBP
title: "Visualizar histórico de atividades (audit log)"
criteria:
  performance:
    target: "Listagem p95 ≤ 250ms com 100 eventos; p99 ≤ 500ms; paginação com cursor/nextToken estável"
    current: "Não testado"
    status: "Pending"
  security:
    target: "RBAC/escopo por projeto/tenant; logs somente leitura; redação de PII/segredos; rate limiting; proteção contra enumeration"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Ordem consistente por (timestamp,id); retenção configurável (p.ex. 12 meses); no data loss (at-least-once) e dedupe por event-id"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Métricas de consulta (lat/p50/p95/p99), acertos de cache, taxa de erro 4xx/5xx; logs com trace-id e project-id; evento audit_log_viewed"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Falta de políticas/implementação de redação de dados sensíveis (AC3)"
    - "Paginação com cursor ainda não validada sob rotação de eventos (AC1)"
</pre>
