<pre>
id: US-017
epic: OBP
date: 20250928
title: "Integrar com ferramentas externas (Google Drive, Slack)"
scope_acs: "Cobrir AC1–AC4 da US-017 (OAuth2, upload em Drive, mensagens Slack, revogação)."
strategy:
  unit:
    - "OAuth2 token flow."
    - "Parsing de webhooks."
  integration:
    - "Conectar conta externa via OAuth2 (mock)."
    - "Upload em Drive e mensagem em Slack."
    - "Revogação desativa integração."
  e2e:
    - "Conectar, usar e revogar integração."
prioritization:
  P0: ["Fluxo OAuth2 e upload Slack/Drive."]
  P1: ["Revogação correta."]
  P2: ["Testes de resiliência de APIs externas."]
data_mocks:
  - "Mocks de Google/Slack APIs."
ci_recommendations:
  - "Tag @integration."
  - "Retries 2x para chamadas externas."
summary:
  total: 16
  unit: 5
  integration: 6
  e2e: 5
  P0: 9
  P1: 4
  P2: 3
</pre>
