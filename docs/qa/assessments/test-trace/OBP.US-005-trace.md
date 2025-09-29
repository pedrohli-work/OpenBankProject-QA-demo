# OBP.US-005-trace.md
id: US-005
epic: OBP
title: "Visualizar dashboard inicial personalizado"
acs:
  - AC1: "Dashboard mostra widgets conforme perfil do usuário"
  - AC2: "Exibe estados: carregando, vazio e erro"
  - AC3: "Preferências alteram layout e persistem entre sessões"
  - AC4: "Dados de outros usuários nunca são exibidos"
tests:
  AC1:
    - "tests/unit/test_dashboard_selectors.py::test_widgets_by_profile"
    - "tests/integration/test_dashboard_aggregator.py::test_entitlements_scope"
  AC2:
    - "tests/e2e/test_dashboard_ui.py::test_loading_empty_error_states"
  AC3:
    - "tests/integration/test_dashboard_prefs.py::test_prefs_persist"
  AC4:
    - GAP: "Falta teste de isolamento de dados entre usuários (P0)"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 1
    high: 0
    medium: 0
    low: 0
