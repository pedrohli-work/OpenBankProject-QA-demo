# OBP.US-008-trace.md
id: US-008
epic: OBP
title: "Definir papéis e permissões no projeto"
acs:
  - AC1: "Owner pode atribuir e remover papéis"
  - AC2: "Permissões respeitam entitlements"
  - AC3: "Alterações refletem imediatamente nas views"
  - AC4: "Usuário sem permissão recebe erro 403"
tests:
  AC1:
    - "tests/integration/test_roles.py::test_assign_remove_roles"
  AC2:
    - "tests/unit/test_permissions.py::test_entitlements_check"
  AC3:
    - GAP: "Falta teste de propagação imediata nas views (P1)"
  AC4:
    - "tests/integration/test_roles.py::test_forbidden_403"
summary:
  total_acs: 4
  covered: 3
  gaps: 1
  severity:
    critical: 0
    high: 0
    medium: 1
    low: 0
