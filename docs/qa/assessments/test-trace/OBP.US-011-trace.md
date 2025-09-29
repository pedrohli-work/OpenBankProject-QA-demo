<pre>
id: US-011
epic: OBP
title: "Atualizar status de tarefas (To Do, Doing, Done)"
acs:
  - AC1: "Owner/Editor pode atualizar status da tarefa"
  - AC2: "Board reflete o novo status imediatamente"
  - AC3: "Histórico de mudanças de status é registrado (timestamp, autor, de/para)"
  - AC4: "Usuário sem permissão (ou não-membro) recebe 403 ao tentar atualizar"
tests:
  AC1:
    - "tests/integration/test_status_update.py::test_owner_editor_can_update_status"
  AC2:
    - "tests/e2e/test_board.py::test_board_reflects_status_change"
  AC3:
    - "tests/integration/test_history.py::test_status_history_persisted"
    - GAP: "Falta teste de concorrência (double update) com lock otimista (P1)"
  AC4:
    - "tests/integration/test_status_update.py::test_forbidden_for_non_member_or_viewer"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 0
    high: 1
    medium: 0
    low: 0
</pre>
