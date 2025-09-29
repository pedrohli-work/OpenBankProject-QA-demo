# OBP.US-002-trace.md
id: US-002
epic: OBP
title: "Login com autenticação segura"
acs:
  - AC1: "Usuário pode fazer login com credenciais válidas"
  - AC2: "Credenciais inválidas retornam erro genérico"
  - AC3: "Após N falhas, lockout temporário"
  - AC4: "Tokens expiram após TTL definido"
tests:
  AC1:
    - "tests/integration/test_login.py::test_login_valid"
  AC2:
    - "tests/integration/test_login.py::test_login_invalid_error"
  AC3:
    - "tests/integration/test_login.py::test_login_lockout"
  AC4:
    - GAP: "Falta teste de expiração de JWT (P0)"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 1
    high: 0
    medium: 0
    low: 0
