<pre>
id: US-016
epic: OBP
title: "Gerar relatórios de progresso do projeto"
date: 20250928
risks:
  tecnico: "2x3=6 → falha na geração → retries + fallback"
  seguranca: "2x3=6 → relatório acessível indevidamente → checagem de roles"
  performance: "3x3=9 → relatórios grandes → paginação + cache"
  dados_privacidade: "2x3=6 → dados sensíveis em PDF/CSV → mascaramento"
  negocio: "2x2=4 → inconsistência de dados → auditoria"
  operacional: "2x2=4 → falha no exportador → redundância"
gate: "FAIL (performance = 9)"
acoes_recomendadas:
  - "Paginação e cache de relatórios"
  - "Verificação de permissões antes do export"
  - "Mascaramento de dados em export"
</pre>
