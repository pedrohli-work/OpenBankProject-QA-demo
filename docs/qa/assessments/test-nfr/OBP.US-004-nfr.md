# OBP.US-004-nfr.md
id: US-004
epic: OBP
title: "Editar perfil de usuário"
criteria:
  performance:
    target: "Upload ≤ 2s p95"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Uploads validados (MIME, antivírus)"
    current: "Não testado"
    status: "Pending"
  reliability:
    target: "Rollback consistente em falhas de upload"
    current: "Não testado"
    status: "Pending"
  observability:
    target: "Logs de falhas de upload claros"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "Pending"
  blockers:
    - "Falta teste de persistência pós-reload"
    - "Falta teste de mensagens de erro"
