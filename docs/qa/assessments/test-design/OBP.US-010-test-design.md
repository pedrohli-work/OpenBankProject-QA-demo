id: US-010
epic: OBP
date: 20250928
title: "Atribuir tarefas a membros do time"
scope_acs: "Cobrir AC1–AC4 da US-010 (atribuição por papéis, exibição no board, notificações, bloqueio de não-membros)."
strategy:
  unit:
    - "Regras de permissão para atribuição."
    - "Atualização de responsável."
  integration:
    - "PUT /tasks/{id}/assign para owner/editor; 403 se não autorizado."
    - "Notificação enviada ao atribuído."
  e2e:
    - "Atribuir e verificar board/alertas."
prioritization:
  P0: ["Permissões corretas; exibição do responsável."]
  P1: ["Notificações confiáveis."]
  P2: ["Concorrência em múltiplas atribuições."]
data_mocks:
  - "Usuários membro e não-membro; simulador de notificações."
ci_recommendations:
  - "Tag @integration."
  - "Retries 1x para notificações."
summary:
  total: 15
  unit: 5
  integration: 6
  e2e: 4
  P0: 8
  P1: 5
  P2: 2
