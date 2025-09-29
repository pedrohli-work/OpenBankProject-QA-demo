<pre>
id: US-013
epic: OBP
title: "Comentar em tarefas e mencionar usuários"
date: 20250928
risks:
  tecnico: "2x2=4 → falha em persistência → retries"
  seguranca: "2x3=6 → spam/mentions indevidas → rate limiting"
  performance: "1x2=2 → excesso de comentários → paginação"
  dados_privacidade: "2x2=4 → menções vazando info → checagem de permissões"
  negocio: "1x2=2 → falha em comentários → impacto baixo"
  operacional: "1x2=2 → falha em notificações → monitoramento"
gate: "CONCERNS (segurança = 6)"
acoes_recomendadas:
  - "Rate limiting em comentários"
  - "Checagem de permissões em menções"
  - "Monitorar filas de notificações"
</pre>
