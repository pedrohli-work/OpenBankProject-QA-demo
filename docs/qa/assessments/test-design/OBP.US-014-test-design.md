# OBP.US-014-test-design.md
<pre>
id: US-014
epic: OBP
date: 20250928
title: "Receber notificações em tempo real"
scope_acs: "Cobrir AC1–AC4 da US-014 (latência ≤2s, escopo, persistência offline, opt-out)."
strategy:
  unit:
    - "Filtro de eventos por usuário."
    - "Persistência local de mensagens."
  integration:
    - "Canal WebSocket/SSE entrega evento em ≤2s."
    - "Apenas eventos de projetos do usuário."
    - "Persistência de notificações offline."
  e2e:
    - "Fluxo simulado: evento → entrega online/offline → opt-out respeitado."
prioritization:
  P0: ["Entrega ≤2s; escopo correto."]
  P1: ["Persistência offline."]
  P2: ["Opt-out avançado."]
data_mocks:
  - "Eventos simulados; conexões instáveis."
ci_recommendations:
  - "Tag @integration."
  - "Retries 1x em falhas de rede."
summary:
  total: 17
  unit: 6
  integration: 6
  e2e: 5
  P0: 10
  P1: 5
  P2: 2
</pre>
