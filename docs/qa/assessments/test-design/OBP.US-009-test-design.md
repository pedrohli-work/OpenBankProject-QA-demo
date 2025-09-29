id: US-009
epic: OBP
date: 20250928
title: "Criar e organizar tarefas no projeto"
scope_acs: "Cobrir AC1–AC4 da US-009 (criação, status inicial, mover colunas, 422)."
strategy:
  unit:
    - "Validação de título e vínculo ao projeto."
    - "Transições de status permitidas."
  integration:
    - "POST /projects/{id}/tasks cria tarefa; 422 inválidos."
    - "Movimentação entre colunas persiste."
  e2e:
    - "Fluxo criar → mover → visualizar board."
prioritization:
  P0: ["Criação válida; 422 inválidos; transições corretas."]
  P1: ["Ordem e paginação."]
  P2: ["Telemetria."]
data_mocks:
  - "Tarefas válidas/inválidas; muitos itens."
ci_recommendations:
  - "Tag @integration; seeds isolados."
  - "Retries 0; IT 30s; E2E 90s."
summary:
  total: 16
  unit: 6
  integration: 6
  e2e: 4
  P0: 9
  P1: 4
  P2: 3
