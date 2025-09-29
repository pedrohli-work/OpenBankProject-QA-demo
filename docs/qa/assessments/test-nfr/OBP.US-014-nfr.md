<pre>
id: US-014
epic: OBP
title: "Receber notificações em tempo real"
criteria:
  performance:
    target: "Entrega p95 ≤ 2s e p99 ≤ 4s; handshake WS/SSE ≤ 1s; throughput de fanout ≥ 5k msgs/min/nó com backpressure"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Autenticação por token no handshake; escopo por projeto/tenant; sem vazamento cross-project; rate limiting e quotas no canal"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Re conexão com exponential backoff; store-and-forward offline; pelo menos uma vez (at-least-once) com dedupe; ordenação por tarefa/conversa"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Métricas de entrega (latency histograms p50/p95/p99), taxa de drop/retry, sessões ativas; logs com trace-id; eventos auditáveis notification_delivered/failed"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Validação de SLO sob carga/fanout (AC1) ainda não coberta"
    - "Testes de isolamento por projeto/tenant em cenários limite (AC2)"
    - "Deduplicação multi-aba/dispositivo após reconexão (AC3)"
</pre>
