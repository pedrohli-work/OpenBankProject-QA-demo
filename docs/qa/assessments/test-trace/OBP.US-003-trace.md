# OBP.US-003-trace.md
id: US-003
epic: OBP
title: "Recuperar senha via email cadastrado"
acs:
  - AC1: "Solicitação envia email mesmo para contas inexistentes"
  - AC2: "Link expira após tempo configurado"
  - AC3: "Token só pode ser usado uma vez"
  - AC4: "Nova senha atende requisitos de força"
tests:
  AC1:
    - "tests/integration/test_password_reset.py::test_neutral_response"
  AC2:
    - "tests/integration/test_password_reset.py::test_token_expiration"
  AC3:
    - "tests/integration/test_password_reset.py::test_token_one_time_use"
  AC4:
    - GAP: "Falta teste de força de senha (P1)"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 0
    high: 1
    medium: 0
    low: 0
