<pre>
id: US-007
epic: OBP
title: "Convidar usuários para um projeto"
date: 20250928
risks:
  tecnico: "2x3=6 → falha no token → testes de expiração"
  seguranca: "3x3=9 → convites reutilizáveis → one-time tokens"
  performance: "1x2=2 → envios em massa → rate limiting"
  dados_privacidade: "2x2=4 → spam em e-mails → validação de domínio"
  negocio: "1x2=2 → convites falhando → fallback manual"
  operacional: "2x2=4 → falha em serviço de email → retries"
gate: "FAIL (risco segurança = 9)"
acoes_recomendadas:
  - "Tokens de convite one-time"
  - "Rate limiting em convites"
  - "Retries para falha de entrega"
</pre>
