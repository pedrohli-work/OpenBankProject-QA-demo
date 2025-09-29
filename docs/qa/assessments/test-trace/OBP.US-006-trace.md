<pre>
id: US-006
epic: OBP
title: "Criar novo projeto"
acs:
  - AC1: "Projeto é criado com título obrigatório"
  - AC2: "Usuário criador é definido como owner"
  - AC3: "Projeto aparece no dashboard após criação"
  - AC4: "Dados inválidos resultam em erro 422"
tests:
  AC1:
    - "tests/unit/test_projects.py::test_required_title"
    - "tests/integration/test_projects_create.py::test_create_ok"
  AC2:
    - "tests/integration/test_projects_create.py::test_owner_assigned"
  AC3:
    - GAP: "Falta E2E de indexação/visibilidade no dashboard (P1)"
  AC4:
    - "tests/integration/test_projects_create.py::test_validation_422"
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
