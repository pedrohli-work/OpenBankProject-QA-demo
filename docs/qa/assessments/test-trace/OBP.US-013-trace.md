# OBP.US-013-trace.md
id: US-013
epic: OBP
title: "Comentar em tarefas e mencionar usuários"
acs:
  - AC1: "Comentários persistidos e exibidos"
  - AC2: "Menções enviam notificação aos usuários mencionados"
  - AC3: "Comentários inválidos retornam 422"
  - AC4: "Usuários não membros não podem comentar"
tests:
  AC1:
    - "tests/integration/test_comments.py::test_add_comment_and_persist"
    - "tests/e2e/test_comments.py::test_comment_visible_in_task"
  AC2:
    - "tests/integration/test_mentions.py::test_notification_sent_on_mention"
    - GAP: "Falta teste de entrega confirmada de notificação (P1)"
  AC3:
    - "tests/integration/test_comments.py::test_invalid_comment_returns_422"
  AC4:
    - "tests/integration/test_comments.py::test_block_non_member_comment"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 0
    high: 1
    medium: 0
    low: 0
