<pre>
id: US-016
epic: OBP
title: "Gerar relatórios de progresso do projeto"
acs:
  - AC1: "Relatório contém status atualizado das tarefas"
  - AC2: "Exportação disponível em PDF e CSV"
  - AC3: "Apenas membros autorizados podem gerar relatórios"
  - AC4: "Erros de geração retornam status adequado"
tests:
  AC1:
    - "tests/integration/test_reports_api.py::test_report_includes_current_task_status"
    - "tests/e2e/test_reports.py::test_report_content_matches_board"
    - GAP: "Falta teste de consistência sob concorrência (tarefas mudando durante a geração) (P2)"
  AC2:
    - "tests/unit/test_report_formatters.py::test_csv_formatter_fields_and_order"
    - "tests/unit/test_report_formatters.py::test_pdf_renderer_basic_layout"
    - "tests/e2e/test_reports.py::test_download_pdf_and_csv"
    - GAP: "Validação de injeção CSV (spreadsheet formula injection) (P1)"
  AC3:
    - "tests/integration/test_reports_permissions.py::test_only_members_with_role_can_generate"
    - "tests/integration/test_reports_permissions.py::test_forbidden_for_non_members_403"
  AC4:
    - "tests/integration/test_reports_api.py::test_propagate_generation_errors_with_http_status"
    - "tests/integration/test_reports_api.py::test_timeout_or_backend_failure_maps_to_503"
summary:
  total_acs: 4
  covered: 3
  gaps: 2
  severity:
    critical: 0
    high: 1
    medium: 1
    low: 0
</pre>
