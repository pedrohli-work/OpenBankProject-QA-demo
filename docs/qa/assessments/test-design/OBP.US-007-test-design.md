<pre>
id: US-007
epic: OBP
date: 20250928
title: "Convidar usuários para um projeto"
scope_acs: "Cobrir AC1–AC4 da US-007 (convite, token único/TTL, aceite, erro em inválido)."
strategy:
  unit:
    - "Geração/validação de token (uso único + TTL)."
    - "Validação de email."
  integration:
    - "POST /projects/{id}/invite envia email (mock) + token."
    - "Aceitar convite adiciona usuário ao projeto."
    - "Convite inválido/expirado → erro."
  e2e:
    - "Owner convida → convidado aceita → acesso concedido."
prioritization:
  P0: ["Token único/TTL; aceite adiciona usuário."]
  P1: ["Idempotência do convite."]
  P2: ["UX de erros."]
data_mocks:
  - "Inbox fake; tokens válido/expirado/usado."
ci_recommendations:
  - "Tag @integration."
  - "Retries 1x em envio de email (mock)."
summary:
  total: 18
  unit: 7
  integration: 7
  e2e: 4
  P0: 10
  P1: 5
  P2: 3
</pre>
