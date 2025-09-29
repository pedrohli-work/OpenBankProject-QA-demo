<pre>```</pre>
id: US-008
epic: OBP
date: 20250928
title: "Definir papéis e permissões no projeto"
scope_acs: "Cobrir AC1–AC4 da US-008 (atribuir/remover papéis, entitlements, 403)."
strategy:
  unit:
    - "Regras de permissão por papel."
    - "Sincronização de entitlements."
  integration:
    - "PUT /projects/{id}/roles altera papéis e reflete nas views."
    - "Tentativa sem permissão → 403."
    - "Escopos não permitem acesso indevido."
  e2e:
    - "Fluxo com diferentes papéis validando acesso a telas."
prioritization:
  P0: ["Permissões corretas e 403."]
  P1: ["Propagação imediata."]
  P2: ["Auditoria de alterações."]
data_mocks:
  - "Conjuntos de usuários (owner/editor/viewer)."
ci_recommendations:
  - "Tag @integration."
  - "Timeout IT 30s; retries 0."
summary:
  total: 17
  unit: 6
  integration: 7
  e2e: 4
  P0: 9
  P1: 5
  P2: 3
```</pre>
