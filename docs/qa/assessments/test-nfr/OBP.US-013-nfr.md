<pre>
id: US-013
epic: OBP
title: "Comentar em tarefas e mencionar usuários"
criteria:
  performance:
    target: "Persistência de comentário p95 ≤ 200ms; notificação de menção enviada ≤ 2s"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Somente membros autenticados podem comentar; bloqueio consistente (403) para não membros"
    current: "OK"
    status: "Pass"
  reliability:
    target: "Entrega consistente de notificações de menção; sem perda de comentários"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Eventos comment_added e user_mentioned registrados; métricas de taxa de erro/latência"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Falta teste de entrega confirmada de notificações de menção (AC2)"
</pre>
