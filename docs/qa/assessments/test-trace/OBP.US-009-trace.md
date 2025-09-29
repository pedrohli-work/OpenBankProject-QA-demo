# OBP.US-009-trace.md
id: US-009
epic: OBP
title: "Criar e organizar tarefas no projeto"
acs:
  - AC1: "Tarefas podem ser criadas com título obrigatório"
  - AC2: "Tarefas têm status inicial 'To Do'"
  - AC3: "Tarefas podem ser movidas entre colunas"
  - AC4: "Dados inválidos resultam em erro 422"
tests:
  AC1:
    - "tests/integration/test_tasks.py::test_create_task_ok"
  AC2:
    - "tests/unit/test_tasks_domain.py::test_default_status_todo"
  AC3:
    - "tests/integration/test_tasks_board.py::test_move_between_columns"
  AC4:
    - GAP: "Falta conjunto abrangente de invalidações (P1)"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 0
    high: 0
    medium: 1
    low: 0
