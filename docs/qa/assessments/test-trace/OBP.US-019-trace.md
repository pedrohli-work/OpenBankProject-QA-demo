# OBP.US-019-trace.md
id: US-019
epic: OBP
title: "Visualizar histórico de atividades (audit log)"
acs:
  - AC1: "Log exibe ações recentes em ordem"
  - AC2: "Log é somente leitura"
  - AC3: "Apenas membros autorizados acessam o log"
  - AC4: "Erros retornam status adequado"
tests:
  AC1:
    - "tests/unit/test_audit_log_ordering.py::test_sorted_desc_by_timestamp"
    - "tests/integration/test_audit_log_api.py::test_returns_recent_actions_in_order"
    - GAP: "Paginação estável com cursor (sem duplicações/perdas entre páginas) (P2)"
  AC2:
    - "tests/integration/test_audit_log_permissions.py::test_write_operations_rejected_405_403"
  AC3:
    - "tests/integration/test_audit_log_permissions.py::test_only_authorized_members_can_access"
    - "tests/e2e/test_audit_log_ui.py::test_non_member_cannot_view_audit_log"
    - GAP: "Redação/mascaramento de campos sensíveis em eventos (PII/segredos) (P1)"
  AC4:
    - "tests/integration/test_audit_log_api.py::test_backend_failure_maps_to_503"
    - "tests/integration/test_audit_log_api.py::test_invalid_query_params_return_400"
summary:
  total_acs: 4
  covered: 3
  gaps: 2
  severity:
    critical: 0
    high: 1
    medium: 1
    low: 0
