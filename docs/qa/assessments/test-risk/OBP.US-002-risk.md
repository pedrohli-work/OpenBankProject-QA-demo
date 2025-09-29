<pre>
id: US-002
epic: OBP
title: "Login com autenticação segura"
date: 20250928
risks:
  tecnico: "2x3=6 → falhas no JWT → validação robusta + rotacionar chaves"
  seguranca: "3x3=9 → brute force se lockout falhar → lockout e monitoramento"
  performance: "2x2=4 → sobrecarga de sessão → otimização de cache"
  dados_privacidade: "2x3=6 → vazamento em tokens → claims mínimos"
  negocio: "1x2=2 → login indisponível → fallback parcial"
  operacional: "2x2=4 → falhas na rotação de tokens → automação"
gate: "FAIL (risco segurança = 9)"
acoes_recomendadas:
  - "Revisar lockout e monitoramento de brute force"
  - "Rotacionar chaves JWT com política definida"
  - "Validar tamanho e claims de tokens"
</pre>
