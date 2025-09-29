<pre> ```id: US-002
epic: OBP
date: 20250928
title: "Login com autenticação segura"
scope_acs: "Cobrir AC1–AC4 da US-002 (login, erro genérico, lockout, TTL/refresh)."
strategy:
  unit:
    - "Comparação de hash de senha."
    - "Geração/expiração de access/refresh tokens."
    - "Contador/backoff de lockout."
    - "Flags de cookie/CSRF (se aplicável)."
  integration:
    - "POST /login válido/inválido; erro genérico sem revelar usuário."
    - "Lockout após N tentativas."
    - "Refresh → novo access; logout → revogação/blacklist."
    - "Entitlements/views aplicadas no dashboard pós-login."
  e2e:
    - "Login → acesso ao dashboard → logout; sessão persiste entre reloads."
prioritization:
  P0: ["Happy path login; lockout; expiração/refresh; revogação."]
  P1: ["Remember-me; múltiplos dispositivos/sessões."]
  P2: ["Alertas de atividade suspeita."]
data_mocks:
  - "Usuário válido/inválido; não verificado; bloqueado."
  - "Provider de hora; storage de sessões/tokens."
ci_recommendations:
  - "Marcar fluxos críticos como @integration."
  - "Retries 1x apenas para falhas transitórias."
  - "Timeouts IT 30s; E2E 120s."
summary:
  total: 24
  unit: 12
  integration: 7
  e2e: 5
  P0: 14
  P1: 6
  P2: 4
```</pre>
