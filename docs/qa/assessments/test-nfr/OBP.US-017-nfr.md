<pre>
id: US-017
epic: OBP
title: "Integrar com ferramentas externas (Google Drive, Slack)"
criteria:
  performance:
    target: "OAuth2 handshake ≤ 2s; upload p95 ≤ 5s (10MB); publicação Slack p95 ≤ 1s; retentativa com backoff exponencial em 429/5xx"
    current: "Não testado"
    status: "Pending"
  security:
    target: "PKCE + state; armazenar tokens criptografados (KMS); escopo mínimo; rotate/refresh seguro; revogação efetiva; assinatura/verificação de webhooks; sanitização de payload"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Idempotência por request-id; fila/retentativa para webhooks; tolerância a falhas de terceiros; circuit breaker; isolamento por provedor"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Métricas de sucesso/erro por provedor, latências p50/p95/p99; logs com trace-id e external-correlation-id; eventos oauth_connected/revoked, drive_uploaded, slack_posted/failed"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Faltam testes de rotação/comprometimento de tokens (AC1)"
    - "Idempotência e backoff robustos em Drive/Slack (AC2/AC3)"
    - "Assinatura/validação de webhooks e revogação total (AC4)"
</pre>
