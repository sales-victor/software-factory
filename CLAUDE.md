# Software Factory

Este projeto utiliza uma arquitetura de desenvolvimento baseada em agentes especializados.

## Objetivo

O objetivo é desenvolver software utilizando uma abordagem semelhante a uma equipe profissional:

- Product/Requirements
- Arquitetura
- UX/UI
- Engenharia de Software
- Backend
- Frontend
- Banco de Dados
- QA
- Segurança
- Code Review
- DevOps

## Princípios

### 1. Não implementar antes de entender

Antes de alterar código:

1. Entender o requisito.
2. Inspecionar o código existente.
3. Identificar padrões existentes.
4. Identificar dependências.
5. Avaliar impacto.
6. Definir a solução.

### 2. Preferir consistência

O código existente é a principal referência.

Não introduzir:

- novos frameworks sem necessidade;
- novos padrões sem justificativa;
- abstrações desnecessárias;
- bibliotecas redundantes.

### 3. Mudanças pequenas

Preferir alterações pequenas, isoladas e fáceis de revisar.

### 4. Segurança desde o início

Toda funcionalidade deve considerar:

- autenticação;
- autorização;
- validação de entrada;
- exposição de dados;
- logs;
- SQL Injection;
- XSS;
- CSRF;
- controle de acesso;
- secrets;
- dependências vulneráveis.

### 5. Testes

Toda alteração relevante deve possuir testes adequados.

### 6. Não inventar

Nunca inventar:

- tabelas;
- colunas;
- APIs;
- endpoints;
- regras de negócio;
- permissões;
- comportamentos existentes.

Quando uma informação não puder ser confirmada, declarar a incerteza.

## Stack padrão

Quando aplicável:

### Backend

- Java 11+
- Spring Boot
- Spring Data
- Spring Security
- JPA/Hibernate
- Maven
- REST

### Frontend

- Angular
- TypeScript
- RxJS
- Angular Material

### Banco

- Oracle
- PostgreSQL

### Infraestrutura

- Docker
- Jenkins
- Linux
- Cloud

## Definition of Done

Uma funcionalidade é considerada concluída somente quando:

- [ ] Requisito entendido
- [ ] Arquitetura avaliada
- [ ] Banco avaliado
- [ ] Backend implementado
- [ ] Frontend implementado
- [ ] Testes implementados
- [ ] Segurança avaliada
- [ ] Code review realizado
- [ ] Build executado
- [ ] Documentação atualizada quando necessário

## Regra fundamental

Nunca alterar código simplesmente para "fazer funcionar".

A solução deve respeitar arquitetura, segurança, manutenção e padrões existentes.