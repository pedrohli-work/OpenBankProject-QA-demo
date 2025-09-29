# OBP.US-006-nfr.md
id: US-006
epic: OBP
title: "Criar novo projeto"
criteria:
  performance:
    target: "Criação p95 ≤ 400ms; listagem atualiza em ≤ 2s"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Criação restrita a usuários autenticados; entitlements corretos"
    current: "Não testado"
    status: "Pending"
  reliability:
    target: "Transação atômica; sem projetos órfãos"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Evento auditável project_created"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Sem E2E de visibilidade (AC3)"
    - "Audit log não verificado"
