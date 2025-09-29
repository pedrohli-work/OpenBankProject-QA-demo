# OBP.US-018-trace.md
id: US-018
epic: OBP
title: "Configurar preferências de notificação"
acs:
  - AC1: "Ativar/desativar canais (email, app, push)"
  - AC2: "Alterações persistem"
  - AC3: "Notificações respeitam as preferências"
  - AC4: "Entradas inválidas retornam 422"
tests:
  AC1:
    - "tests/integration/test_preferences_api.py::test_toggle_channels_email_app_push"
    - "tests/unit/test_preferences_validation.py::test_supported_channels_only"
  AC2:
    - "tests/integration/test_preferences_api.py::test_persist_user_preferences"
    - "tests/e2e/test_notifications_preferences.py::test_prefs_survive_logout_login"
  AC3:
    - "tests/e2e/test_notifications_preferences.py::test_delivery_respects_user_preferences"
    - GAP: "Cenários combinados (ex.: app on + email off + push off) em eventos múltiplos (P1)"
  AC4:
    - "tests/integration/test_preferences_api.py::test_invalid_payload_returns_422"
    - "tests/unit/test_preferences_validation.py::test_reject_unknown_fields_and_values"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 0
    high: 1
    medium: 0
    low: 0
