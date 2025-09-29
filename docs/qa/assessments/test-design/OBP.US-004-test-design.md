id: US-004
epic: OBP
date: 20250928
title: "Editar perfil de usuário"
scope_acs: "Cobrir AC1–AC4 da US-004 (alterar nome/ prefs; upload válido; persistência; erros claros)."
strategy:
  unit:
    - "Validação de campos; normalização de nome."
    - "Whitelist de preferências."
    - "Validação MIME/tamanho; geração de thumbnail."
  integration:
    - "PUT /profile com e sem imagem (mock S3/GCS)."
    - "Atualização atômica + rollback em falha do upload."
    - "Headers/cache-control corretos."
  e2e:
    - "Editar perfil completo; preview/substituição da foto; persistência após reload."
prioritization:
  P0: ["Segurança de upload e validações.", "Atualização atômica de dados + foto."]
  P1: ["Preferências avançadas; preview client-side."]
  P2: ["Compressão/lazy transformations."]
data_mocks:
  - "Imagens válidas (jpg/png), grandes (>5MB), tipo proibido."
  - "Storage, serviço de imagens e CDN mocks."
ci_recommendations:
  - "Tag @integration para fluxos com storage."
  - "Retries 1x para upload."
  - "Timeouts IT 45s; E2E 120s."
summary:
  total: 23
  unit: 10
  integration: 7
  e2e: 6
  P0: 12
  P1: 7
  P2: 4
