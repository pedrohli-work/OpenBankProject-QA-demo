# OBP.US-014-risk.md
id: US-014
epic: OBP
title: "Receber notificações em tempo real"
date: 20250928
risks:
  tecnico: "2x3=6 → falha em WebSocket/SSE → fallback para polling"
  seguranca: "2x3=6 → vazamento de eventos → filtrar por projeto"
  performance: "3x3=9 → sobrecarga em conexões → escalabilidade horizontal"
  dados_privacidade: "2x2=4 → eventos sensíveis → mascaramento"
  negocio: "2x2=4 → falhas em notificações → perda de confiança"
  operacional: "2x2=4 → instabilidade em fila → retries e alertas"
gate: "FAIL (performance = 9)"
acoes_recomendadas:
  - "Escalar infraestrutura para conexões"
  - "Fallback de polling"
  - "Filtrar eventos por escopo"
