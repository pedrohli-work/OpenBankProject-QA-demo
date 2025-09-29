# OBP.US-002-nfr.md
id: US-002
epic: OBP
title: "Login com autenticação segura"
criteria:
  performance:
    target: "Login ≤ 400ms p95"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Lockout configurado, JWT expira corretamente"
    current: "Não testado"
    status: "Pending"
  reliability:
    target: "99% logins válidos em 1ª tentativa"
    current: "Não testado"
    status: "Pending"
  observability:
    target: "Logs de falha mascarados"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "Pending"
  blockers:
    - "Falta teste de expiração JWT"
