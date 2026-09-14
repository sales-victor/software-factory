# Software Factory Plugin

Plugin de desenvolvimento multi-agente para Claude Code. A sessão principal atua como orchestrator; agentes especializados recebem contexto pronto e devolvem resposta compacta.

## Fluxo

```
/software-factory:factory <pedido>
  discovery (1x) → .factory/context.md
  plano + tier   → .factory/plan.md, factory.json
  linha de produção conforme tier
  fix loop → gates → final-report.md
```

| Tier | Quando | Linha |
|------|--------|-------|
| quick | bugfix, 1–3 arquivos | dev → test → code-reviewer |
| standard | feature em uma camada | architect → dev(s) → qa → security → code-reviewer → build |
| full | cross-camada, schema, infra | architecture → ux-ui → database → contracts → backend → frontend → qa → security → code-reviewer → devops → build |

## Skills

| Skill | Função |
|-------|--------|
| `factory` | abre/continua uma ordem e orquestra tudo |
| `factory-status` | mostra `factory.json`, regenera `board.md` |
| `factory-test [escopo]` | roda testes/build com os comandos de `context.md` |
| `factory-review` | code-reviewer sobre o diff da ordem |
| `factory-security` | security sobre o diff da ordem |
| `factory-fix [ids]` | corrige issues OPEN por severidade |

## Agents

| Agent | Modelo | Escreve código |
|-------|--------|----------------|
| architect | sonnet | não |
| software-engineer | sonnet | sim (tier quick / cross) |
| backend-dev | sonnet | sim |
| frontend-dev | sonnet | sim |
| ux-ui | sonnet | não |
| dba | sonnet | migrations |
| qa | sonnet | testes |
| security | sonnet | não |
| code-reviewer | opus | não |
| devops | sonnet | infra |

Todos seguem o mesmo contrato: recebem `context.md`, não refazem discovery, gravam artifact em `.factory/stages/<stage>.md`, respondem no formato compacto.

## Estado (`.factory/`)

```
context.md      discovery único (stack, comandos, padrões, arquivos relevantes)
plan.md         objetivo, requisitos, critérios de aceite, tier, etapas
factory.json    fonte de verdade: stages, gates, issues[], baseCommit, filesChanged
stages/*.md     artifact de cada etapa
final-report.md relatório curto
board.md        gerado a partir do factory.json
```
