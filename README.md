# Desafio Técnico – Desenvolvedor (.NET + React)

Este desafio tem como objetivo avaliar sua capacidade de **entender requisitos de negócio**, **modelar uma solução**, **organizar o código** e **entregar uma aplicação funcional e bem estruturada**.

O foco não é apenas “fazer funcionar”, mas **como você pensa e estrutura a solução**.

---

## Contexto do problema

Uma empresa precisa de um **sistema simples de controle de tickets de suporte interno**.

Esse sistema será usado para registrar solicitações, acompanhar o andamento do trabalho e organizar prioridades.  
Não há necessidade de integração com sistemas externos ou notificações.

---

## Stack obrigatória

- **Backend:** .NET 8 (ASP.NET Core Web API)
- **Frontend:** React (preferencialmente com TypeScript)
- **Banco de dados:** relacional (PostgreSQL, MySQL, SQL Server, etc.)
- **ORM:** livre (EF Core, NHibernate, Dapper, outro — escolha consciente)

---

## Requisitos de negócio

### 1) Acesso ao sistema

- O sistema deve possuir autenticação
- Não é necessário implementar cadastro de usuários
- Os usuários devem estar pré-cadastrados diretamente no banco de dados (seed inicial)
- As credenciais desses usuários devem ser informadas no README para fins de teste
- Apenas usuários autenticados podem acessar o sistema e realizar ações

---

### 2) Tickets de suporte

O sistema deve permitir o gerenciamento de **tickets**, que representam solicitações de suporte.

Funcionalidades esperadas:

- Criar um novo ticket informando:
  - um título
  - uma descrição
  - uma prioridade
  - um usuário responsável
- Editar um ticket existente
- Excluir um ticket  
  > Diferencial: exclusão lógica (*soft delete*)

---

### 3) Fluxo de status

Todo ticket possui um **status**, que representa seu estágio de atendimento.

Regras:
- Um ticket nasce em um estado inicial
- O status deve evoluir de forma **sequencial**
- Não é permitido pular etapas ou voltar para estados anteriores
- Tickets finalizados não podem mais ser alterados

---

### 4) Listagem e consulta

O sistema deve permitir consultar tickets com:

- Paginação no backend
- Ordenação por data de criação (mais recentes primeiro)
- Filtros por:
  - status
  - prioridade
  - responsável (quando aplicável)
- Busca textual por título e descrição

---

## Frontend

O frontend deve contemplar:

- Tela de login
- Tela de listagem de tickets
  - filtros
  - busca
  - paginação
- Tela de detalhe do ticket
  - edição (quando permitido)
  - alteração de status
  - atribuição de responsável (quando permitido)

Estados de loading, erro e ausência de dados devem ser tratados.

---

## Requisitos técnicos e de qualidade

- Validações devem ser feitas **no backend**
- Erros devem retornar status HTTP apropriado (`400`, `401`, `403`, `404`)
- Datas importantes devem ser geradas e controladas no backend
- Código organizado e legível

---

## Organização da solução (diretriz)

É esperado que a solução tenha **separação clara de responsabilidades**.

Sugerimos o uso de conceitos inspirados em **DDD**, como:

- Camada de domínio com regras de negócio
- Infraestrutura isolando acesso a dados e autenticação
- Controllers finos, sem regra de negócio

> Não é necessário DDD “acadêmico”. O importante é clareza, intenção e organização.

---

## Diferenciais (opcional)

Escolha **1 ou 2**, no máximo:

- Testes automatizados (unitários ou integração)
- Docker / docker-compose (API + banco)
- CI simples (build + testes)
- README explicando decisões técnicas

---

## Entrega

- Repositório público no GitHub
- README contendo:
  - como rodar o backend e frontend
  - como configurar o banco e aplicar migrations
  - usuários de teste (se aplicável)
- Não é necessário deploy em produção

---

Boa sorte 🚀  
