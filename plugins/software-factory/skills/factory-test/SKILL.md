---
name: factory-test
description: Executa os testes apropriados para a stack do projeto e atualiza o QA Gate da Software Factory.
disable-model-invocation: true
---

# Factory Test

Leia:

.factory/factory.json
.factory/project-plan.md

Identifique a stack automaticamente.

Não invente comandos.

Procure:

package.json
pom.xml
build.gradle
pytest.ini
pyproject.toml
Dockerfile
docker-compose.yml
etc.

Execute os testes existentes e apropriados.

Exemplos:

Angular:
npm test
npm run build

Java:
mvn test
mvn verify

Python:
pytest

Use os comandos realmente existentes no projeto.

Registre:

- testes executados
- testes aprovados
- testes falhos
- testes ignorados
- build
- erros

Atualize:

.factory/stages/qa.md
.factory/factory.json
.factory/board.md

Se testes críticos falharem:

QA Gate = FAILED

Não declare READY.