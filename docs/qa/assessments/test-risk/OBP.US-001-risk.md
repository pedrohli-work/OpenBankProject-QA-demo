<pre>
id: US-001
epic: OBP
title: "Autenticar via Direct Login e validar users/current"
date: 20250928
risks:
  tecnico: "3x3=9 → flutuação do sandbox → retries/backoff controlados"
  seguranca: "2x4=8 → segredos em logs → masking + revisão de logging"
  performance: "2x3=6 → latência alta → cache seletivo e timeouts"
  dados_privacidade: "2x3=6 → PII → limitar campos em logs"
  negocio: "1x3=3 → indisponibilidade do sandbox → mocks para contingência"
  operacional: "2x2=4 → rotatividade de credenciais → doc e rotação"
gate: "FAIL (risco técnico = 9)"
acoes_recomendadas:
  - "Implementar masking obrigatório em logs"
  - "Configurar retry/backoff com limites"
  - "Marcar testes reais como @integration"
</pre>
