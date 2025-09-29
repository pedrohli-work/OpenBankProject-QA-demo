# OBP.US-019-risk.md
id: US-019
epic: OBP
title: "Visualizar histórico de atividades (audit log)"
date: 20250928
risks:
  tecnico: "2x2=4 → falha em ordenação → testes unitários"
  seguranca: "2x3=6 → vazamento de logs → restrição de acesso"
  performance: "2x3=6 → logs grandes → paginação e arquivamento"
  dados_privacidade: "2x3=6 → PII em logs → mascaramento"
  negocio: "2x2=4 → log incompleto → perda de auditoria"
  operacional: "2x2=4 → falha em sync → alertas"
gate: "CONCERNS (segurança/performance/dados = 6)"
acoes_recomendadas:
  - "Paginação e arquivamento de logs"
  - "Restrição de acesso"
  - "Mascarar PII nos logs"
