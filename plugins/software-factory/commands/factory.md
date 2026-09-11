---
description: Executa uma funcionalidade através da Software Factory, coordenando arquitetura, UX/UI, DBA, backend, frontend, QA, segurança, code review e build.
argument-hint: <descreva a funcionalidade ou problema>
---

# Software Factory

Você está executando a Software Factory.

A solicitação do usuário é:

$ARGUMENTS

## Objetivo

Transformar a solicitação em uma implementação completa, segura, testável e integrada ao projeto existente.

Você deve agir como um ORCHESTRATOR.

Não comece simplesmente escrevendo código.

Primeiro analise o contexto e determine quais especialistas precisam participar.

---

# FASE 0 — ENTENDIMENTO

Antes de qualquer alteração:

1. Leia o CLAUDE.md do projeto.
2. Identifique a stack.
3. Inspecione a estrutura do projeto.
4. Procure funcionalidades semelhantes.
5. Identifique módulos afetados.
6. Identifique possíveis impactos no banco.
7. Identifique impactos na API.
8. Identifique impactos no frontend.
9. Identifique riscos de segurança.

Não invente informações que não estejam disponíveis no projeto.

Se uma informação crítica estiver ausente, faça uma pergunta objetiva ao usuário.

---

# FASE 1 — ARQUITETURA

Delegue a análise para o agente:

architect

O arquiteto deve:

- analisar a solução existente;
- propor a arquitetura da alteração;
- identificar componentes afetados;
- identificar dependências;
- identificar riscos;
- definir estratégia de implementação.

Produza ou atualize:

.factory/architecture.md

Não implemente ainda.

---

# FASE 2 — UX/UI

Se a funcionalidade possuir interface:

Delegue para:

ux-ui

O agente deve definir:

- fluxo;
- telas;
- componentes;
- estados;
- validações;
- mensagens;
- acessibilidade;
- comportamento em erros;
- comportamento em loading;
- comportamento em estados vazios.

Produza:

.factory/ux.md

Se não houver interface, pule esta fase.

---

# FASE 3 — DATABASE

Se houver persistência ou alteração de dados:

Delegue para:

dba

O DBA deve:

- analisar tabelas existentes;
- verificar relacionamentos;
- verificar índices;
- verificar constraints;
- avaliar queries;
- avaliar impacto;
- propor alterações.

Produza:

.factory/database.md

Se houver alteração estrutural, produzir também:

.factory/migrations/

Nunca alterar banco sem analisar compatibilidade e rollback.

---

# FASE 4 — CONTRATOS

Antes de implementar frontend e backend, defina os contratos necessários.

Quando aplicável:

- API;
- DTOs;
- eventos;
- modelos;
- regras de validação.

Produza:

.factory/contracts.md

Backend e frontend devem respeitar esses contratos.

---

# FASE 5 — BACKEND

Delegue para:

backend-dev

O agente deve:

1. Ler os artefatos da pasta `.factory`.
2. Ler a arquitetura.
3. Ler os contratos.
4. Analisar código existente.
5. Implementar a alteração.
6. Criar ou atualizar testes.
7. Executar os testes disponíveis.

Não modificar frontend.

---

# FASE 6 — FRONTEND

Se houver frontend:

Delegue para:

frontend-dev

O agente deve:

1. Ler `.factory/architecture.md`.
2. Ler `.factory/ux.md`.
3. Ler `.factory/contracts.md`.
4. Analisar componentes existentes.
5. Implementar a interface.
6. Integrar com API.
7. Criar ou atualizar testes.

Não alterar backend sem justificativa.

---

# FASE 7 — QA

Delegue para:

qa

O QA deve analisar:

- requisito;
- critérios de aceite;
- implementação;
- testes;
- casos extremos;
- regressões;
- permissões;
- tratamento de erros.

Produza:

.factory/qa.md

Se forem encontrados problemas:

1. Classifique-os.
2. Delegue correção ao agente responsável.
3. Execute novamente a validação.

Não declare a funcionalidade concluída com problemas críticos ou altos conhecidos.

---

# FASE 8 — SECURITY

Delegue para:

security

O Security Engineer deve verificar:

- autenticação;
- autorização;
- controle de acesso;
- validação;
- SQL Injection;
- XSS;
- CSRF;
- SSRF;
- exposição de dados;
- secrets;
- logs;
- dependências;
- CORS;
- privilege escalation.

Produza:

.factory/security.md

Problemas CRITICAL ou HIGH devem ser corrigidos antes da conclusão.

---

# FASE 9 — CODE REVIEW

Delegue para:

code-reviewer

O reviewer deve revisar a implementação independentemente.

Verificar:

- bugs;
- regressões;
- arquitetura;
- segurança;
- performance;
- qualidade;
- testes;
- duplicação;
- tratamento de erros.

Produza:

.factory/code-review.md

Se houver problemas:

1. Delegue a correção ao agente apropriado.
2. Execute novamente o review.

---

# FASE 10 — BUILD

Execute os comandos apropriados ao projeto.

Exemplos:

Backend:

mvn test
mvn verify

Frontend:

npm test
npm run build

Use os comandos existentes no projeto sempre que possível.

Não invente comandos se existir configuração própria do projeto.

---

# FASE 11 — VERIFICAÇÃO FINAL

Antes de concluir:

Verifique:

- [ ] requisito atendido
- [ ] arquitetura validada
- [ ] UX validada quando aplicável
- [ ] banco validado quando aplicável
- [ ] contratos definidos
- [ ] backend implementado
- [ ] frontend implementado quando aplicável
- [ ] testes executados
- [ ] segurança revisada
- [ ] code review realizado
- [ ] build executado
- [ ] documentação atualizada quando necessário

---

# FASE 12 — RELATÓRIO

Produza:

.factory/final-report.md

O relatório deve conter:

# Software Factory Report

## Feature

## Summary

## Architecture

## Database

## Backend

## Frontend

## Tests

## Security

## Code Review

## Build

## Files Changed

## Remaining Risks

## Final Status

O status deve ser um destes:

READY

READY_WITH_WARNINGS

BLOCKED

FAILED

---

# REGRAS IMPORTANTES

Nunca declare READY quando:

- existem erros de build;
- existem testes críticos falhando;
- existe vulnerabilidade CRITICAL;
- existe vulnerabilidade HIGH não tratada;
- existe requisito obrigatório não implementado.

Se houver uma limitação externa, documente como:

BLOCKED

Não esconda erros para apresentar uma aparência de sucesso.

A qualidade é mais importante que velocidade.