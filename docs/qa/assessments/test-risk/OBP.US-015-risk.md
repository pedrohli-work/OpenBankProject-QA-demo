# OBP.US-015-risk.md
id: US-015
epic: OBP
title: "Pesquisar tarefas, projetos e usuários"
date: 20250928
risks:
  tecnico: "2x3=6 → falha no índice → rebuild automático"
  seguranca: "2x3=6 → vazamento de dados → aplicar entitlements"
  performance: "3x3=9 → consultas lentas → índices e cache"
  dados_privacidade: "2x3=6 → termos revelando info → sanitização"
  negocio: "2x2=4 → resultados incorretos → impacto moderado"
  operacional: "2x2=4 → índice desatualizado → monitoramento"
gate: "FAIL (performance = 9)"
acoes_recomendadas:
  - "Indexação e cache adequados"
  - "Filtros de permissão estritos"
  - "Sanitização de termos de busca"
