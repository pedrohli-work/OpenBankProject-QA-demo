<pre>
id: US-006
epic: OBP
title: "Criar novo projeto"
date: 20250928
risks:
  tecnico: "2x3=6 → projeto sem owner → validação obrigatória"
  seguranca: "1x2=2 → criação não autorizada → verificar entitlements"
  performance: "1x2=2 → volume alto → indexação eficiente"
  dados_privacidade: "1x2=2 → metadados incorretos → sanitização"
  negocio: "2x2=4 → criação falha → retries no client"
  operacional: "1x2=2 → dados não indexados → monitoramento"
gate: "CONCERNS (risco técnico = 6)"
acoes_recomendadas:
  - "Owner obrigatório na criação"
  - "Monitoramento de indexação"
  - "Revisar entitlements de criação"
</pre>
