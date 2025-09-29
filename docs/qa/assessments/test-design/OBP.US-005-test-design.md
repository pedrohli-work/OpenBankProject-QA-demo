<pre>```id: US-005
epic: OBP
date: 20250928
title: "Visualizar dashboard inicial personalizado"
scope_acs: "Cobrir AC1–AC4 da US-005 (widgets por perfil; estados; persistência; isolamento de dados)."
strategy:
  unit:
    - "Seletores/agregadores; memoização; formatação."
    - "Feature flags; guards de autorização."
  integration:
    - "Agregadores com respostas 200/206/500; paginação."
    - "Checagem de escopo por entitlement/view."
    - "Degradação graciosa em falhas parciais."
  e2e:
    - "Login → render do dashboard; estados vazio/erro; preferencias persistem."
prioritization:
  P0: ["Autorização por escopo; estados de erro/carregamento."]
  P1: ["Personalização persistente; performance básica."]
  P2: ["Métricas avançadas."]
data_mocks:
  - "Serviços: tarefas, projetos, notificações."
  - "Usuário sem dados; usuário com carga grande."
ci_recommendations:
  - "Tag @integration nos agregadores."
  - "Retries 1x em 5xx; IT 45s; E2E 150s."
summary:
  total: 25
  unit: 12
  integration: 7
  e2e: 6
  P0: 14
  P1: 8
  P2: 3
```</pre>
