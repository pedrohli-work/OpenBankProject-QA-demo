# OBP.US-008-nfr.md
id: US-008
epic: OBP
title: "Definir papéis e permissões no projeto"
criteria:
  performance:
    target: "Aplicação de role refletida em ≤ 2s nas views"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Zero bypass de permissões em testes @integration"
    current: "Não testado"
    status: "Pending"
  reliability:
    target: "Consistência de roles; auditoria completa"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Eventos role_assigned/role_removed"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Sem teste de propagação imediata (AC3)"
    - "Logs de auditoria não validados"
