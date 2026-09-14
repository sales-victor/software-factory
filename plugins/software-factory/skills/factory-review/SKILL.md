---
name: factory-review
description: Revisão independente do diff da ordem ativa pelo agente code-reviewer; registra findings como issues no factory.json e atualiza o Review Gate.
---

# Factory Review

Leia `.factory/factory.json`, `.factory/plan.md`, `.factory/context.md`.

Escopo: `git diff <baseCommit> --stat` + arquivos alterados (`filesChanged`). Não revise o repositório inteiro.

Delegue para `code-reviewer` com:

- objetivo
- conteúdo de `context.md`
- critérios de aceite de `plan.md`
- lista de arquivos do diff (`path`)
- artifact esperado: `.factory/stages/code-review.md`
- "Responda no formato compacto"

Para cada finding: adicione entrada em `factory.json.issues` (id sequencial, `severity`, `source: REVIEW`, `status: OPEN`, `file`, `problem`, `fix`).

`gates.review`: `PASSED` se não houver CRITICAL/HIGH abertos; senão `FAILED`.

Não corrija. Correção: `/software-factory:factory-fix`.

Responda: gate + lista `path:line: SEVERITY: problema`.
