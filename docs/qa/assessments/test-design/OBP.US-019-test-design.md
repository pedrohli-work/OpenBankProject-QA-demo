# OBP.US-019-test-design.md
id: US-019
epic: OBP
date: 20250928
title: "Visualizar histórico de atividades (audit log)"
scope_acs: "Cobrir AC1–AC4 da US-019 (exibição, somente leitura, permissões, erros)."
strategy:
  unit:
    - "Ordenação de eventos."
  integration:
    - "GET /projects/{id}/audit-log retorna log ordenado."
    - "Apenas autorizados acessam."
  e2e:
    - "Visualizar histórico no UI."
prioritization:
  P0: ["Logs exibidos corretamente; somente leitura."]
  P1: ["Permissões consistentes."]
  P2: ["Performance sob carga."]
data_mocks:
  - "Projetos com logs curtos/longos."
ci_recommendations:
  - "Tag @integration."
  - "Timeout IT 30s; E2E 90s."
summary:
  total: 12
  unit: 3
  integration: 5
  e2e: 4
  P0: 7
  P1: 3
  P2: 2
