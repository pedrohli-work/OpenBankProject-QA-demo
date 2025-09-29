<pre>
id: US-010
epic: OBP
title: "Atribuir tarefas a membros do time"
acs:
  - AC1: "Owner ou editor pode atribuir tarefa"
  - AC2: "Tarefa mostra responsável no board"
  - AC3: "Notificação enviada ao usuário atribuído"
  - AC4: "Usuário não membro não pode ser atribuído"
tests:
  AC1:
    - "tests/integration/test_assign.py::test_assign_by_owner_or_editor"
  AC2:
    - "tests/e2e/test_board.py::test_assignee_visible"
  AC3:
    - GAP: "Falta teste de notificação entregue/confirmada (P1)"
  AC4:
    - "tests/integration/test_assign.py::test_assign_block_non_member"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 0
    high: 0
    medium: 1
    low: 0
</pre>
