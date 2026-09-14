---
name: factory-test
description: Roda testes e build do projeto usando os comandos registrados em .factory/context.md e atualiza os gates qa e build. Aceita escopo direcionado como argumento.
---

# Factory Test

Leia `.factory/factory.json` e `.factory/context.md`.

Argumento opcional: `$ARGUMENTS` = escopo direcionado (ex.: `-Dtest=FaturaServiceTest`, `--include=**/x.spec.ts`). Sem argumento = suíte completa + build.

Comandos: use SOMENTE os listados em `context.md` (vindos do CLAUDE.md / manifests do projeto). Não invente comandos.

Cuidados:

- Nunca rode comando que fica em watch mode (`ng test` sem `--watch=false`, `npm run watch`, `ng serve`). Prefira `--watch=false --browsers=ChromeHeadless` ou typecheck (`npx tsc --noEmit`).
- Projeto sem suíte ativa: registre "sem suíte" — não é falha.
- Comando acima de 10 min: interrompa e registre.

Registre em `.factory/stages/qa.md` (append, seção `## Execução <data>`): comando, aprovados/falhos/ignorados, build, erros (só a linha decisiva de cada erro, não o log inteiro).

Atualize `factory.json`: `gates.qa` e `gates.build`. Teste crítico falhando → gate `FAILED`; nunca declare READY.

Responda:

```
TESTS: <cmd> → ok|fail (n passed, n failed, n skipped)
BUILD: <cmd> → ok|fail
FAIL: path:line: erro
```
