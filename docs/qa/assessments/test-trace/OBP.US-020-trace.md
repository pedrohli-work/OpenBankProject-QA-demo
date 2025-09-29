# OBP.US-020-trace.md
id: US-020
epic: OBP
title: "Exportar dados do projeto (CSV, PDF)"
acs:
  - AC1: "Exportação em CSV e PDF funciona"
  - AC2: "Apenas membros autorizados podem exportar"
  - AC3: "Exportação inclui dados atuais"
  - AC4: "Exportações inválidas retornam erro adequado"
tests:
  AC1:
    - "tests/unit/test_export_formatters.py::test_csv_columns_and_escape"
    - "tests/unit/test_export_formatters.py::test_pdf_renderer_basic_layout"
    - "tests/e2e/test_export_flow.py::test_download_csv_and_pdf_success"
    - GAP: "Proteção contra fórmula CSV (e.g., =, +, -, @ no início da célula) (P1)"
  AC2:
    - "tests/integration/test_export_permissions.py::test_only_authorized_roles_can_export"
    - "tests/integration/test_export_permissions.py::test_non_member_403"
  AC3:
    - "tests/integration/test_export_data_freshness.py::test_export_matches_current_project_state"
    - "tests/e2e/test_export_flow.py::test_export_after_updates_reflects_latest_data"
    - GAP: "Consistência sob concorrência (tarefas sendo atualizadas durante export) com snapshot estável (P2)"
  AC4:
    - "tests/integration/test_export_api.py::test_invalid_params_return_400"
    - "tests/integration/test_export_api.py::test_backend_failure_maps_to_503"
summary:
  total_acs: 4
  covered: 3
  gaps: 2
  severity:
    critical: 0
    high: 1
    medium: 1
    low: 0
