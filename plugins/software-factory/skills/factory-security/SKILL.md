---
name: factory-security
description: Auditoria de segurança do diff da ordem ativa pelo agente security; registra findings como issues no factory.json e atualiza o Security Gate.
---

# Factory Security

Leia `.factory/factory.json`, `.factory/context.md`.

Escopo: `git diff <baseCommit>` + arquivos alterados. Amplie para o repositório só quando um finding exigir rastrear (ex.: endpoint novo → conferir `SecurityConfig`/guards existentes).

Delegue para `security` com:

- objetivo
- conteúdo de `context.md` (inclui modelo de auth/perfis do projeto)
- lista de arquivos do diff
- artifact esperado: `.factory/stages/security.md`
- "Responda no formato compacto"

Para cada finding: adicione entrada em `factory.json.issues` (`source: SECURITY`).

`gates.security`: `FAILED` se houver CRITICAL ou HIGH aberto; senão `PASSED`.

Não corrija. Correção: `/software-factory:factory-fix`.

Responda: gate + lista `path:line: SEVERITY: problema`.
