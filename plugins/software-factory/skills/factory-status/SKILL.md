---
name: factory-review
description: Executa uma revisão completa da implementação atual usando o Code Reviewer e atualiza o quadro da Software Factory.
disable-model-invocation: true
---

# Factory Review

Leia:

.factory/factory.json
.factory/project-plan.md
.factory/board.md

Inspecione o código atual.

Delegue a revisão para `code-reviewer`.

Avalie:

- arquitetura
- organização
- qualidade
- duplicação
- manutenção
- bugs
- performance
- tratamento de erros
- segurança
- testes
- aderência aos requisitos

Crie ou atualize:

.factory/stages/code-review.md

Crie issues quando necessário.

Atualize:

.factory/factory.json
.factory/board.md

Não corrija automaticamente os problemas.

Para correção use `/software-factory:factory-fix`.

Informe:

- problemas encontrados
- severity
- arquivos afetados
- recomendações
- Review Gate