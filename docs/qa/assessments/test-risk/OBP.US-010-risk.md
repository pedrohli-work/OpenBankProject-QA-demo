<pre>
id: US-010
epic: OBP
title: "Atribuir tarefas a membros do time"
date: 20250928
risks:
  tecnico: "2x3=6 → falha em concorrência → locks otimistas"
  seguranca: "2x3=6 → atribuição a não membros → validação de papéis"
  performance: "1x2=2 → notificações lentas → filas assíncronas"
  dados_privacidade: "1x2=2 → dados em notificação → limitar payload"
  negocio: "2x2=4 → tarefas não atribuídas → alertas"
  operacional: "2x2=4 → falha em fila de notificações → retries"
gate: "CONCERNS (técnico/segurança = 6)"
acoes_recomendadas:
  - "Validação de papéis antes da atribuição"
  - "Locks otimistas em concorrência"
  - "Retries em fila de notificações"
</pre>
