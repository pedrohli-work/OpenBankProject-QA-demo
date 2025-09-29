<pre>
id: US-003
epic: OBP
title: "Recuperar senha via email cadastrado"
date: 20250928
risks:
  tecnico: "2x3=6 → falha no TTL → clock sync e testes de expiração"
  seguranca: "3x3=9 → reutilização de token → invalidação imediata"
  performance: "1x2=2 → volume de resets → throttling"
  dados_privacidade: "2x3=6 → resposta revelando conta → neutral response"
  negocio: "1x2=2 → resets indisponíveis → suporte manual"
  operacional: "2x2=4 → e-mails não entregues → monitoramento e retries"
gate: "FAIL (risco segurança = 9)"
acoes_recomendadas:
  - "Neutral response em forgot password"
  - "Tokens one-time + TTL estrito"
  - "Monitoramento de entregas de email"
</pre>
