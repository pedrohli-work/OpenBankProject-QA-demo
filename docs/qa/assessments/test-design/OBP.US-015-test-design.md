# OBP.US-015-test-design.md
id: US-015
epic: OBP
date: 20250928
title: "Pesquisar tarefas, projetos e usuários"
scope_acs: "Cobrir AC1–AC4 da US-015 (relevância, permissões, paginação, erro 400)."
strategy:
  unit:
    - "Ranking básico."
    - "Filtros de permissões."
  integration:
    - "GET /search retorna resultados corretos."
    - "Paginação funciona."
    - "Termos inválidos → 400."
  e2e:
    - "Pesquisar globalmente com diferentes papéis."
prioritization:
  P0: ["Relevância básica; respeitar permissões."]
  P1: ["Paginação robusta."]
  P2: ["Performance sob carga."]
data_mocks:
  - "Indices com tarefas, projetos, usuários variados."
ci_recommendations:
  - "Tag @integration."
  - "Timeout IT 30s; E2E 120s."
summary:
  total: 18
  unit: 6
  integration: 6
  e2e: 6
  P0: 10
  P1: 5
  P2: 3
