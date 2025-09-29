# OBP.US-005-risk.md
id: US-005
epic: OBP
title: "Visualizar dashboard inicial personalizado"
date: 20250928
risks:
  tecnico: "2x3=6 → agregadores falhando → fallback por widget"
  seguranca: "2x3=6 → dados cruzados → testes de isolamento de sessão"
  performance: "3x3=9 → dados grandes → paginação e cache"
  dados_privacidade: "2x2=4 → exposição de dados → restrição de escopos"
  negocio: "2x2=4 → falha em widgets críticos → métricas de uso"
  operacional: "1x2=2 → serviços filhos instáveis → retries seletivos"
gate: "FAIL (risco performance = 9)"
acoes_recomendadas:
  - "Adicionar paginação e cache em agregadores"
  - "Testes de isolamento entre usuários"
  - "Fallback por widget no dashboard"
