# OBP.US-008-risk.md
id: US-008
epic: OBP
title: "Definir papéis e permissões no projeto"
date: 20250928
risks:
  tecnico: "2x3=6 → falha em roles → testes de propagação"
  seguranca: "3x3=9 → escalada de privilégios → revisão de entitlements"
  performance: "1x2=2 → latência de sync → otimizar cache"
  dados_privacidade: "1x2=2 → excesso de permissões → princípio de menor privilégio"
  negocio: "2x2=4 → inconsistência de roles → logs de auditoria"
  operacional: "2x2=4 → falha em sync → alertas"
gate: "FAIL (risco segurança = 9)"
acoes_recomendadas:
  - "Auditoria de entitlements"
  - "Testes automáticos de roles"
  - "Alertas de inconsistências"
