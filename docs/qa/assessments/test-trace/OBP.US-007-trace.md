# OBP.US-007-trace.md
id: US-007
epic: OBP
title: "Convidar usuários para um projeto"
acs:
  - AC1: "Owner envia convite para email válido"
  - AC2: "Convite gera token único com expiração"
  - AC3: "Convite aceito adiciona usuário ao projeto"
  - AC4: "Convite inválido/expirado gera erro"
tests:
  AC1:
    - "tests/unit/test_invites.py::test_email_validation"
    - "tests/integration/test_invites.py::test_send_invite_mock_email"
  AC2:
    - "tests/unit/test_invites.py::test_token_generation_ttl_onetime"
  AC3:
    - "tests/integration/test_invites.py::test_accept_invite_adds_member"
  AC4:
    - GAP: "Falta teste de convite expirado/invalidado (P0)"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 1
    high: 0
    medium: 0
    low: 0
