<pre>
id: US-004
epic: OBP
title: "Editar perfil de usuário"
acs:
  - AC1: "Usuário pode alterar nome e preferências"
  - AC2: "Upload de foto aceita apenas formatos/tamanhos válidos"
  - AC3: "Alterações persistem após reload"
  - AC4: "Mensagens claras em caso de erro"
tests:
  AC1:
    - "tests/unit/test_profile.py::test_update_preferences"
  AC2:
    - "tests/integration/test_profile.py::test_upload_validations"
  AC3:
    - GAP: "Falta teste de persistência pós-reload (P1)"
  AC4:
    - GAP: "Falta teste de mensagens de erro claras (P2)"
summary:
  total_acs: 4
  covered: 2
  gaps: 2
  severity:
    critical: 0
    high: 1
    medium: 0
    low: 1
</pre>
