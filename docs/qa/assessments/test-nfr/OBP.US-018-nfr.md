# OBP.US-018-nfr.md
id: US-018
epic: OBP
title: "Configurar preferências de notificação"
criteria:
  performance:
    target: "Atualização de preferências p95 ≤ 150ms; leitura p95 ≤ 100ms; avaliação de preferência em roteamento de notificação ≤ 5ms/evento (cache)"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Somente o próprio usuário (ou admin) pode alterar; validação de escopo; proteção contra mass assignment; audit log de mudanças"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Persistência idempotente por user-id; consistência leitura-após-escrita ≤ 1s; fallback seguro (se preferência ausente → default 'off' para canais externos)"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Eventos preference_updated; métricas de acerto de cache e latência de roteamento; logs com trace-id e user-id (sem PII de conteúdo)"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Cobertura parcial para combinações de canais e múltiplos eventos (AC3)"
    - "Validações de escopo/mass assignment não totalmente testadas"
