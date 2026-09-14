---
name: factory-fix
description: Corrige as issues OPEN do factory.json por severidade, delegando ao agente do domínio, com teste direcionado por issue e revalidação ao final.
---

# Factory Fix

Leia `.factory/factory.json` e `.factory/context.md`. Filtre `issues[]` com `status: OPEN`. Ordem: CRITICAL → HIGH → MEDIUM → LOW.

Argumento opcional: `$ARGUMENTS` = ids específicos (ex.: `ISSUE-003 ISSUE-005`).

Para cada issue:

1. marque `IN_PROGRESS`
2. agente pelo domínio: arquitetura→`architect` · banco→`dba` · backend→`backend-dev` · frontend→`frontend-dev` · teste→`qa` · segurança→`security` · infra→`devops` · UX→`ux-ui`
3. delegue com: issue (`problem`, `file`, `fix`), conteúdo de `context.md`, arquivos afetados, "Responda no formato compacto"
4. teste direcionado (classe/spec do arquivo tocado) — não a suíte completa
5. `RESOLVED` só com evidência; sem solução → `BLOCKED` + motivo

Após todas:

- suíte completa + build via `/software-factory:factory-test` (uma vez)
- `/software-factory:factory-review` só se alguma correção tocou arquitetura/contratos
- `/software-factory:factory-security` só se alguma correção tocou auth/input/segredos
- atualize `factory.json` (issues, gates)

Nunca altere requisitos para fazer uma issue desaparecer.

Responda: tabela `id | severity | RESOLVED/BLOCKED | arquivo`.
