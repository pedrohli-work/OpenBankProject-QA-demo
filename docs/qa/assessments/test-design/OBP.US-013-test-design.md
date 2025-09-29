<pre>
id: US-013
epic: OBP
date: 20250928
title: "Comentar em tarefas e mencionar usuários"
scope_acs: "Cobrir AC1–AC4 da US-013 (persistência, menções, erros 422, permissões)."
strategy:
  unit:
    - "Validação de comentários."
    - "Parsing de menções."
  integration:
    - "POST /tasks/{id}/comments → comentário salvo e menções notificam."
    - "Usuário não autorizado → 403."
  e2e:
    - "Comentar e verificar notificação da menção."
prioritization:
  P0: ["Persistência; menções corretas; 403 não autorizados."]
  P1: ["Validação robusta de entradas."]
  P2: ["UX contra spam."]
data_mocks:
  - "Comentários válidos/inválidos; usuários mencionados existentes/não existentes."
ci_recommendations:
  - "Tag @integration."
  - "Retries 0; IT 30s; E2E 90s."
summary:
  total: 15
  unit: 5
  integration: 5
  e2e: 5
  P0: 9
  P1: 4
  P2: 2
</pre>
