<pre>
id: US-009
epic: OBP
title: "Criar e organizar tarefas no projeto"
date: 20250928
risks:
  tecnico: "2x3=6 → falha em transição de status → testes de regras"
  seguranca: "1x2=2 → acesso não autorizado → checagem de project ownership"
  performance: "2x2=4 → board grande → paginação"
  dados_privacidade: "1x2=2 → dados inválidos → sanitização"
  negocio: "2x2=4 → board inconsistente → rollback"
  operacional: "1x2=2 → seeds quebradas → monitoramento"
gate: "CONCERNS (risco técnico = 6)"
acoes_recomendadas:
  - "Validação estrita de status"
  - "Rollback em falhas de board"
  - "Paginação em tarefas"
</pre>
