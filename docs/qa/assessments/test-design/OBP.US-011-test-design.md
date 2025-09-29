<pre>
id: US-011
epic: OBP
date: 20250928
title: "Atualizar status de tarefas (To Do, Doing, Done)"
scope_acs: "Cobrir AC1–AC4 da US-011 (autorização, refletir no board, histórico, 403)."
strategy:
  unit:
    - "Validação de transições permitidas."
    - "Registro de histórico de mudanças."
  integration:
    - "PUT /tasks/{id}/status com papéis válidos/ inválidos (403)."
    - "Board reflete alteração; histórico persistido."
  e2e:
    - "Fluxo de mudança de status e persistência após reload."
prioritization:
  P0: ["Autorização correta e 403 para não autorizados; persistência de status."]
  P1: ["Histórico consistente."]
  P2: ["Eventos de telemetria."]
data_mocks:
  - "Tarefas em diferentes estados; papéis variados."
ci_recommendations:
  - "Tag @integration; seeds isolados."
  - "Retries 0; IT 30s; E2E 90s."
summary:
  total: 14
  unit: 5
  integration: 5
  e2e: 4
  P0: 8
  P1: 4
  P2: 2
</pre>
