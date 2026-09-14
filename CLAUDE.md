# Software Factory

Plugin de desenvolvimento multi-agente para Claude Code. O usuário abre uma ordem com `/software-factory:factory <pedido>`; a sessão principal atua como orchestrator e delega a agentes especializados.

## Princípios

1. **Entender antes de implementar** — requisito, código existente, padrões, dependências, impacto, só então solução.
2. **Consistência** — o código existente é a referência. Sem framework, padrão, abstração ou biblioteca nova sem justificativa.
3. **Mudanças pequenas** — isoladas, fáceis de revisar.
4. **Segurança desde o início** — autenticação, autorização, validação, exposição de dados, logs, injection, XSS, CSRF, secrets, dependências.
5. **Testes** — toda alteração relevante tem teste.
6. **Não inventar** — tabelas, colunas, APIs, endpoints, regras, permissões, comportamentos. Incerteza é declarada.

## Economia de tokens

- Discovery acontece **uma vez** (orchestrator) e vira `.factory/context.md`. Agentes não refazem discovery.
- Delegação sempre lista arquivos (`path:linhas`); agente não lê fora da lista sem necessidade.
- Agente grava artifact em `.factory/stages/` e responde só no formato compacto (`STAGE / RESULT / ARTIFACT / FILES / FINDINGS / NOTES`).
- QA, Security e Code Review analisam `git diff <baseCommit>`, não o repositório.
- `.factory/factory.json` é a única fonte de verdade (stages, gates, issues). `board.md` é gerado.
- Tier por tamanho da ordem: `quick` (bugfix, 1–3 arquivos) · `standard` (feature em uma camada) · `full` (cross-camada, schema, infra).
- Testes direcionados no fix loop; suíte completa + build uma vez no Build gate.
- QA → Security → Code Review em sequência, nunca em paralelo.

## Stack

Não é fixa. Vem do `CLAUDE.md` e dos manifests do projeto onde a factory roda, registrada em `context.md`. Os agentes são especializados (Java/Spring, Angular, SQL) mas não assumem versão, SGBD nem pipeline.

## Definition of Done

Requisito entendido · arquitetura avaliada · banco avaliado · backend/frontend implementados · testes · segurança avaliada · code review · build executado · documentação atualizada quando necessário. Etapas fora do tier ficam `SKIPPED` com justificativa.

## Regra fundamental

Nunca alterar código só para "fazer funcionar". A solução respeita arquitetura, segurança, manutenção e padrões existentes.
