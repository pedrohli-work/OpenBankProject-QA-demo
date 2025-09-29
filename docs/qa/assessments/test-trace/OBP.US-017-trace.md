# OBP.US-017-trace.md
id: US-017
epic: OBP
title: "Integrar com ferramentas externas (Google Drive, Slack)"
acs:
  - AC1: "Usuário conecta conta externa via OAuth2"
  - AC2: "É possível fazer upload em Google Drive a partir da plataforma"
  - AC3: "Plataforma publica mensagens no Slack"
  - AC4: "Revogação de integração funciona (tokens invalidados e acesso removido)"
tests:
  AC1:
    - "tests/integration/test_oauth2_flow.py::test_authorization_code_success"
    - "tests/integration/test_oauth2_flow.py::test_token_refresh_success"
    - GAP: "Rotação automática de refresh_token e deteção de token comprometido (P1)"
  AC2:
    - "tests/integration/test_drive_integration.py::test_upload_file_to_drive_folder"
    - "tests/e2e/test_external_integrations.py::test_upload_from_ui_visible_in_drive"
    - GAP: "Retentativa com backoff em 429/5xx e idempotência por request-id (P2)"
  AC3:
    - "tests/integration/test_slack_integration.py::test_post_message_to_channel"
    - "tests/e2e/test_external_integrations.py::test_publish_message_from_ui"
    - GAP: "Formatação/escape seguro de conteúdo (avoid @here/@channel spam) (P1)"
  AC4:
    - "tests/integration/test_oauth2_revoke.py::test_revoke_removes_access_and_webhooks"
    - "tests/e2e/test_external_integrations.py::test_revocation_stops_actions"
summary:
  total_acs: 4
  covered: 3
  gaps: 3
  severity:
    critical: 0
    high: 2
    medium: 1
    low: 0
