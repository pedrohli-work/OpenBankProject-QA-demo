# OBP.US-018-risk.md
id: US-018
epic: OBP
title: "Configurar preferências de notificação"
date: 20250928
risks:
  tecnico: "2x2=4 → falha em persistência → retries"
  seguranca: "2x3=6 → bypass de preferências → validação robusta"
  performance: "1x2=2 → carga alta em updates → otimização"
  dados_privacidade: "2x3=6 → dados ignorados → mascaramento"
  negocio: "2x2=4 → preferências ignoradas → má experiência"
  operacional: "1x2=2 → falha em sync → monitoramento"
gate: "CONCERNS (segurança/dados = 6)"
acoes_recomendadas:
  - "Validação estrita de preferências"
  - "Testes de sync em diferentes canais"
  - "Monitorar falhas de notificação"
