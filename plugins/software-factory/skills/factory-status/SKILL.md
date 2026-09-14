---
name: factory-status
description: Mostra o estado da ordem de produção ativa (tier, stages, gates, issues, próximo passo) a partir de .factory/factory.json e regenera board.md.
disable-model-invocation: true
---

# Factory Status

Leia `.factory/factory.json`.

Se não existir: responda "Não existe nenhuma ordem de produção ativa neste projeto." e pare. Não crie ordem.

Mostre:

1. ordem, feature, tier, status, etapa atual
2. stages com estado
3. gates
4. issues por severity (id, status, resumo de uma linha)
5. próximo passo recomendado (uma linha)

Regenere `.factory/board.md` a partir do JSON (tabelas: stages, gates, issues).

Não modifique código nem `factory.json` (exceto para corrigir JSON inválido, avisando).
