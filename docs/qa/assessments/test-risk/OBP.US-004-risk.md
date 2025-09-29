<pre>
id: US-004
epic: OBP
title: "Editar perfil de usuário"
date: 20250928
risks:
  tecnico: "2x3=6 → falha em rollback → testes de consistência"
  seguranca: "2x3=6 → upload malicioso → validação MIME/antivírus"
  performance: "2x2=4 → uploads grandes → compressão e limites"
  dados_privacidade: "2x2=4 → metadados em fotos → limpeza de EXIF"
  negocio: "1x2=2 → indisponibilidade do perfil → fallback"
  operacional: "1x2=2 → falha em storage → redundância"
gate: "CONCERNS (riscos técnicos/segurança = 6)"
acoes_recomendadas:
  - "Validar uploads com antivírus"
  - "Rollback transacional no update"
  - "Monitorar tempo de resposta de storage"
</pre>
