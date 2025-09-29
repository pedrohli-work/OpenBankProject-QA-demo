<pre>
id: US-012
epic: OBP
title: "Anexar arquivos e documentos a tarefas"
criteria:
  performance:
    target: "Upload p95 ≤ 3s para arquivos até 10MB; latência de associação ≤ 200ms; listagem de anexos ≤ 200ms"
    current: "Não testado"
    status: "Pending"
  security:
    target: "Whitelist de MIME/extension; varredura antivírus; tamanho máx 10MB; URLs assinadas com expiração; checagem de permissão no download/remover"
    current: "Parcial"
    status: "At Risk"
  reliability:
    target: "Idempotência em reenvio; rollback em falha; tratamento de indisponibilidade do storage (retry com backoff e circuit breaker); consistência metadata↔storage"
    current: "Parcial"
    status: "At Risk"
  observability:
    target: "Eventos attachment_uploaded/attachment_deleted; métricas de taxa de erro/latência/tamanho; logs com trace-id (sem PII/conteúdo)"
    current: "Não testado"
    status: "Pending"
summary:
  overall: "At Risk"
  blockers:
    - "Sem testes de antivírus/scan de malware (AC1)"
    - "Cenário de storage indisponível sem cobertura robusta (AC2)"
</pre>
