---
name: factory-fix
description: Analisa as issues abertas da Software Factory, seleciona os agentes responsáveis, corrige os problemas e executa a validação novamente.
disable-model-invocation: true
---

# Factory Fix

Leia:

.factory/factory.json
.factory/board.md
.factory/issues/
.factory/stages/qa.md
.factory/stages/security.md
.factory/stages/code-review.md

Liste todas as issues OPEN.

Prioridade:

1. CRITICAL
2. HIGH
3. MEDIUM
4. LOW

Para cada issue:

1. entenda o problema
2. identifique o domínio
3. selecione o agente adequado
4. forneça contexto
5. aplique a correção
6. execute testes relacionados
7. valide a correção
8. altere status para RESOLVED

Mapeamento:

Architecture
→ architect

UX/UI
→ ux-ui

Database
→ dba

Backend
→ backend-dev

Frontend
→ frontend-dev

Testing
→ qa

Security
→ security

Code quality
→ code-reviewer

Infrastructure
→ devops

Após as correções:

1. execute /factory-test internamente
2. execute revisão quando necessário
3. execute security novamente se a correção afetar segurança
4. atualize factory.json
5. atualize board.md

Nunca marque uma issue como RESOLVED sem validar a correção.

Se uma issue não puder ser corrigida:

marque:

BLOCKED

e explique o motivo.

Não altere requisitos para fazer uma issue desaparecer.