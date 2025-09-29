# OBP.US-012-risk.md
id: US-012
epic: OBP
title: "Anexar arquivos e documentos a tarefas"
date: 20250928
risks:
  tecnico: "2x3=6 → corrupção de anexos → checksums"
  seguranca: "3x3=9 → upload malicioso → antivírus e validação MIME"
  performance: "2x2=4 → arquivos grandes → compressão e limites"
  dados_privacidade: "2x3=6 → PII em anexos → criptografia e restrição"
  negocio: "1x2=2 → anexos indisponíveis → fallback manual"
  operacional: "2x2=4 → falha em storage → redundância"
gate: "FAIL (segurança = 9)"
acoes_recomendadas:
  - "Validação estrita de anexos"
  - "Antivírus obrigatório"
  - "Redundância em storage"
