# OBP.US-012-trace.md
id: US-012
epic: OBP
title: "Anexar arquivos e documentos a tarefas"
acs:
  - AC1: "Aceitar apenas formatos permitidos"
  - AC2: "Falha de upload não compromete a tarefa"
  - AC3: "Anexo visível após upload bem-sucedido"
  - AC4: "Remoção de anexo é possível"
tests:
  AC1:
    - "tests/unit/test_attachments_validation.py::test_accept_only_whitelisted_mime_types"
    - "tests/unit/test_attachments_validation.py::test_reject_disallowed_extensions"
    - GAP: "Falta teste de antivírus/scan de malware no upload (P1)"
  AC2:
    - "tests/integration/test_attachments_api.py::test_upload_failure_does_not_modify_task"
    - "tests/integration/test_attachments_api.py::test_partial_failure_rolls_back_metadata"
    - GAP: "Falta teste de indisponibilidade do storage com fallback/retry/circuit breaker (P1)"
  AC3:
    - "tests/e2e/test_attachments_flow.py::test_attachment_visible_on_task_after_upload"
    - "tests/integration/test_attachments_api.py::test_metadata_persisted_after_upload"
  AC4:
    - "tests/integration/test_attachments_api.py::test_delete_attachment_by_owner_or_editor"
    - "tests/e2e/test_attachments_flow.py::test_remove_attachment_updates_ui_and_metadata"
summary:
  total_acs: 4
  covered: 3
  gaps: 2
  severity:
    critical: 0
    high: 2
    medium: 0
    low: 0
