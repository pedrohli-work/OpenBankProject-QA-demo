<pre>```id: US-003
epic: OBP
date: 20250928
title: "Recuperar senha via email cadastrado"
scope_acs: "Cobrir AC1–AC4 da US-003 (neutral response; TTL; uso único; força de senha)."
strategy:
  unit:
    - "Geração/TTL/uso-único de token de reset."
    - "Política de força de senha."
    - "Invalidar token após uso; clock-control."
    - "Limiters por IP/email."
  integration:
    - "POST /password/forgot sempre 200/202 + email (mock inbox)."
    - "POST /password/reset com token válido/expirado/inválido."
    - "Auditoria de reset e masking de PII em logs."
  e2e:
    - "Fluxo: forgot → capturar email → reset → login com nova senha; token inválido bloqueado."
prioritization:
  P0: ["Neutral response; token one-time + TTL; reset completo."]
  P1: ["Força de senha; histórico."]
  P2: ["UX de mensagens."]
data_mocks:
  - "Inbox fake para email; storage de tokens; clock fake."
ci_recommendations:
  - "Tag @integration nos dois endpoints."
  - "Retries 0 para forgot; 1 para reset."
  - "Timeouts IT 30s; E2E 90s."
summary:
  total: 22
  unit: 11
  integration: 6
  e2e: 5
  P0: 12
  P1: 6
  P2: 4
```</pre>
