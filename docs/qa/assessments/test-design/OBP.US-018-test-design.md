# OBP.US-018-test-design.md
id: US-018
epic: OBP
date: 20250928
title: "Configurar preferências de notificação"
scope_acs: "Cobrir AC1–AC4 da US-018 (ativar/desativar canais, persistência, respeitar preferências, erros 422)."
strategy:
  unit:
    - "Validação de entradas."
    - "Persistência de preferências."
  integration:
    - "PUT /users/{id}/preferences salva preferências."
    - "Notificações respeitam preferências."
  e2e:
    - "Alterar preferências e validar notificações recebidas."
prioritization:
  P0: ["Persistência e respeito às preferências."]
  P1: ["Validação robusta."]
  P2: ["Simulação cross-device."]
data_mocks:
  - "Usuários com diferentes preferências."
ci_recommendations:
  - "Tag @integration."
  - "Retries 0; IT 30s; E2E 90s."
summary:
  total: 14
  unit: 5
  integration: 5
  e2e: 4
  P0: 8
  P1: 4
  P2: 2
