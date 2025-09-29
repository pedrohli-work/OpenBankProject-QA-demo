<pre>```id: US-006
epic: OBP
date: 20250928
title: "Criar novo projeto"
scope_acs: "Cobrir AC1–AC4 da US-006 (criação, owner, dashboard, validação 422)."
strategy:
  unit:
    - "Validação de payload (título obrigatório)."
    - "Atribuição de owner ao criador."
  integration:
    - "POST /projects sucesso; 422 inválidos."
    - "Projeto aparece em dashboard."
    - "Entitlements asseguram visibilidade."
  e2e:
    - "Criar projeto e verificar presença no dashboard."
prioritization:
  P0: ["Criação e owner; 422 inválidos."]
  P1: ["Indexação imediata."]
  P2: ["Telemetria."]
data_mocks:
  - "Projetos válidos/inválidos; diferentes papéis."
ci_recommendations:
  - "Tag @integration; DB efêmero."
  - "Retries 1x em 5xx."
summary:
  total: 16
  unit: 6
  integration: 6
  e2e: 4
  P0: 8
  P1: 5
  P2: 3
```</pre>
