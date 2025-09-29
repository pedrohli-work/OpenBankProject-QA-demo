<pre>```
id: US-001
epic: OBP
date: 20250928
title: "Autenticar via Direct Login e validar users/current"
scope_acs: "Cobrir AC1–AC4 da US-001 (Direct Login e users/current)."
strategy:
  unit:
    - "Constrói header DirectLogin corretamente."
    - "Parse/armazenamento do token."
    - "Mapeamento erros HTTP → domínios de erro."
    - "Masking de segredos em logs/utilidades."
  integration:
    - "POST /my/logins/direct válido → 200 + token (OBP sandbox)."
    - "GET /obp/v3.1.0/users/current com token válido → 200 + usuário."
    - "Credenciais inválidas → 401 tratado (sem segredos)."
    - "Retry/backoff para 5xx; timeouts e logs mascarados."
  e2e:
    - "Configurar .env → login → users/current → verificação."
prioritization:
  P0:
    - "Login 200 + token; users/current 200; header correto (unit)."
  P1:
    - "401 inválido; retries/backoff 5xx; timeouts."
  P2:
    - "Roteiro E2E manual; casos de latência/observabilidade."
data_mocks:
  - ".env: OBP_BASE_URL, OBP_USERNAME, OBP_PASSWORD, OBP_CONSUMER_KEY"
  - "Mocks para unit; sandbox real para integration (@integration)."
ci_recommendations:
  - "Separar unit vs @integration."
  - "Retries limitados; timeouts definidos; logs com masking."
summary:
  total: 10
  unit: 4
  integration: 4
  e2e: 2
  P0: 5
  P1: 3
  P2: 2
```</pre>
