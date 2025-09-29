<pre>
id: US-017
epic: OBP
title: "Integrar com ferramentas externas (Google Drive, Slack)"
date: 20250928
risks:
  tecnico: "2x3=6 → falha em integração OAuth2 → retries e refresh"
  seguranca: "3x3=9 → tokens externos expostos → storage seguro"
  performance: "2x2=4 → lentidão de APIs externas → fila assíncrona"
  dados_privacidade: "2x3=6 → dados enviados indevidamente → scoping"
  negocio: "2x2=4 → falha em integração → impacto moderado"
  operacional: "2x2=4 → dependência de terceiros → alertas e fallback"
gate: "FAIL (segurança = 9)"
acoes_recomendadas:
  - "Armazenar tokens externos com criptografia"
  - "Retries + refresh de OAuth2"
  - "Fallback quando APIs externas falharem"
</pre>
