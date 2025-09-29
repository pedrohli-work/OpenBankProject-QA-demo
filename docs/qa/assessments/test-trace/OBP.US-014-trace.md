<pre>
id: US-014
epic: OBP
title: "Receber notificações em tempo real"
acs:
  - AC1: "Notificações entregues em até 2s"
  - AC2: "Usuário recebe apenas eventos de projetos onde participa"
  - AC3: "Notificações persistem offline e são sincronizadas ao reconectar"
  - AC4: "Preferência de opt-out é respeitada"
tests:
  AC1:
    - "tests/integration/test_realtime.py::test_delivery_under_2s_ws_sse"
    - "tests/e2e/test_notifications_flow.py::test_realtime_delivery_latency"
    - GAP: "Teste de SLO em carga (p95/p99) com fanout alto e backpressure (P1)"
  AC2:
    - "tests/unit/test_event_filter.py::test_scope_by_project_membership"
    - "tests/integration/test_multitenancy.py::test_no_cross_project_events"
    - "tests/e2e/test_security_isolation.py::test_prevent_leak_between_projects"
  AC3:
    - "tests/integration/test_offline_queue.py::test_store_and_replay_on_reconnect"
    - "tests/e2e/test_offline_sync.py::test_disconnect_and_resync_without_loss"
    - GAP: "Deduplicação multi-aba/dispositivo ao reprocessar backlog (P2)"
  AC4:
    - "tests/unit/test_optout.py::test_optout_flag_respected"
    - "tests/integration/test_subscription.py::test_unsubscribe_stop_stream"
    - "tests/e2e/test_preferences.py::test_toggle_optout_no_more_events"
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
