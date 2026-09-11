---
name: factory-status
description: Mostra o estado atual da produção da Software Factory, incluindo pipeline, agentes, gates, issues e próximo passo.
disable-model-invocation: true
---

# Factory Status

Leia:

.factory/factory.json
.factory/board.md

Se `.factory/factory.json` não existir:

Informe:

"Não existe nenhuma ordem de produção ativa neste projeto."

Não crie uma produção automaticamente.

Caso exista:

1. mostre ordem atual
2. mostre status geral
3. mostre progresso
4. mostre pipeline
5. mostre agentes
6. mostre gates
7. mostre issues por severity
8. mostre etapa atual
9. mostre próximo passo recomendado

Atualize `board.md` se estiver inconsistente com `factory.json`.

Não modifique código.