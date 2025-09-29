<pre>
id: US-020
epic: OBP
date: 20250928
title: "Exportar dados do projeto (CSV, PDF)"
scope_acs: "Cobrir AC1–AC4 da US-020 (exportação, permissões, dados atuais, erros)."
strategy:
  unit:
    - "Formatação CSV/PDF."
  integration:
    - "GET /projects/{id}/export gera CSV/PDF."
    - "Apenas membros autorizados exportam."
  e2e:
    - "Exportar e abrir arquivos."
prioritization:
  P0: ["Exportação válida; permissões."]
  P1: ["Validação de formatos."]
  P2: ["Performance em projetos grandes."]
data_mocks:
  - "Projetos pequenos/grandes."
ci_recommendations:
  - "Tag @integration."
  - "Timeout IT 45s; E2E 120s."
summary:
  total: 13
  unit: 4
  integration: 5
  e2e: 4
  P0: 8
  P1: 3
  P2: 2
</pre>
