# OBP.US-011-nfr.md
id: US-011
epic: OBP
title: "Atualizar status de tarefas (To Do, Doing, Done)"
criteria:
  performance:
    target: "Atualização de status p95 ≤ 200ms; propagação no board ≤ 1s"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Somente Owner/Editor podem atualizar; 403 consistente para demais perfis"
    current: "Parcial"
    status: "Pending"
  reliability:
    target: "Sem conflito em dupla atualização (lock otimista/versionamento); histórico imutável"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Evento task_status_changed + auditoria completa (quem/quando/de→para) com métricas"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Teste de concorrência (double update) com lock otimista ausente (AC3)"
    - "Eventos/telemetria task_status_changed ainda não implementados"
