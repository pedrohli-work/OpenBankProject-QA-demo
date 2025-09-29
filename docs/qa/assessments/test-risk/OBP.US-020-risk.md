<pre>
id: US-020
epic: OBP
title: "Exportar dados do projeto (CSV, PDF)"
date: 20250928
risks:
  tecnico: "2x3=6 → falha em export → retries e fallback"
  seguranca: "2x3=6 → export acessível a não membros → validação"
  performance: "3x3=9 → export de projetos grandes → paginação"
  dados_privacidade: "3x3=9 → dados sensíveis exportados → mascaramento e escopos"
  negocio: "2x2=4 → export inconsistente → auditoria"
  operacional: "2x2=4 → falha em geração → redundância"
gate: "FAIL (performance e dados = 9)"
acoes_recomendadas:
  - "Mascarar dados sensíveis"
  - "Paginar grandes exports"
  - "Verificar permissões antes da exportação"
</pre>
