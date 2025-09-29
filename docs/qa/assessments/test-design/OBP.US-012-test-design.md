# OBP.US-012-test-design.md
<pre>```
id: US-012
epic: OBP
date: 20250928
title: "Anexar arquivos e documentos a tarefas"
scope_acs: "Cobrir AC1–AC4 da US-012 (formatos permitidos, resiliência, visibilidade, remoção)."
strategy:
  unit:
    - "Validação MIME/tamanho; nomes seguros."
  integration:
    - "POST /tasks/{id}/attachments (upload) e DELETE (remoção) com storage mock."
    - "Falha de upload não compromete a tarefa."
  e2e:
    - "Adicionar, visualizar e remover anexo na UI."
prioritization:
  P0: ["Validação de upload; resiliência a falhas."]
  P1: ["Visibilidade imediata no board."]
  P2: ["Preview/transformações."]
data_mocks:
  - "Arquivos válidos/grandes/proibidos; storage/CDN mocks."
ci_recommendations:
  - "Tag @integration; fixtures reusáveis."
  - "Retries 1x para upload; IT 45s; E2E 120s."
summary:
  total: 16
  unit: 5
  integration: 6
  e2e: 5
  P0: 9
  P1: 4
  P2: 3
```</pre>
