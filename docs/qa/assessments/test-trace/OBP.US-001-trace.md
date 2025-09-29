# OBP.US-001-trace.md
id: US-001
epic: OBP
title: "Autenticar via Direct Login e validar users/current"
acs:
  - AC1: "Login retorna 200 + token"
  - AC2: "users/current com token válido retorna usuário"
  - AC3: "Credenciais inválidas retornam 401 sem segredos"
  - AC4: "Logs mascaram segredos; retries/timeouts para 5xx"
tests:
  AC1:
    - "tests/unit/test_obp_login.py::test_build_directlogin_header"
    - "tests/integration/test_obp_login.py::test_login_success"
  AC2:
    - "tests/integration/test_obp_users.py::test_get_current_user"
  AC3:
    - "tests/integration/test_obp_login.py::test_login_invalid_credentials"
  AC4:
    - GAP: "Falta teste de logs mascarados (P1)"
    - GAP: "Falta teste de retries/backoff (P1)"
summary:
  total_acs: 4
  covered: 3
  gaps: 2
  severity:
    critical: 0
    high: 0
    medium: 2
    low: 0
