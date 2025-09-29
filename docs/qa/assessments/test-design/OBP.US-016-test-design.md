<pre>
id: US-016
epic: OBP
date: 20250928
title: "Gerar relatórios de progresso do projeto"
scope_acs: "Cobrir AC1–AC4 da US-016 (status atualizado, export PDF/CSV, permissões, erros)."
strategy:
  unit:
    - "Formatação de relatórios."
    - "Validação de filtros."
  integration:
    - "GET /projects/{id}/reports exporta PDF/CSV."
    - "Permissões respeitadas."
  e2e:
    - "Gerar e baixar relatório completo."
prioritization:
  P0: ["Conteúdo correto; permissões."]
  P1: ["Exportação multi-formato."]
  P2: ["Performance com grandes volumes."]
data_mocks:
  - "Projetos pequenos/grandes; papéis variados."
ci_recommendations:
  - "Tag @integration."
  - "Timeout IT 45s; E2E 120s."
summary:
  total: 15
  unit: 5
  integration: 5
  e2e: 5
  P0: 9
  P1: 4
  P2: 2
</pre>
