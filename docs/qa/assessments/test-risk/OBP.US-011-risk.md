<pre>
id: US-011
epic: OBP
title: "Atualizar status de tarefas (To Do, Doing, Done)"
date: 20250928
risks:
  tecnico: "2x3=6 → falha em transições → validação de estados"
  seguranca: "2x3=6 → update sem permissão → checagem de papéis"
  performance: "1x2=2 → alto volume de updates → otimização de queries"
  dados_privacidade: "1x2=2 → exposição de histórico → controle de acesso"
  negocio: "2x2=4 → status incorretos → impacto no fluxo do time"
  operacional: "1x2=2 → auditoria incompleta → monitoramento"
gate: "CONCERNS (técnico/segurança = 6)"
acoes_recomendadas:
  - "Validação de transições"
  - "Auditoria robusta"
  - "Testes de permissão automáticos"
</pre>
