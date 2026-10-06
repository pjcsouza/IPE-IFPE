# Decisões de Arquitetura e Stack

Este documento registra as decisões principais para o desenvolvimento didático do projeto IPE-IFPE, sem perder o foco em simplicidade e facilidade de entendimento.

## 1. Stack principal

- Backend: Express.js
- Banco de dados: PostgreSQL
- Frontend: React
- Comunicação: REST API
- ORM: Prisma
- Autenticação: JWT (JSON Web Token)
- Estilização do frontend: Tailwind CSS
- Gerenciamento de estado: Context API do React
- Roteamento do frontend: React Router
- Ambiente local: Docker Compose

## 2. Estrutura proposta

### Backend

- src/
  - app.js
  - server.js
  - routes/
  - controllers/
  - services/
  - middlewares/
  - utils/
  - config/
  - prisma/

### Frontend

- src/
  - components/
  - pages/
  - routes/
  - contexts/
  - hooks/
  - services/
  - styles/
  - utils/

### Banco de dados

- prisma/
  - schema.prisma
  - migrations/
  - seed.js

## 3. Padrões de desenvolvimento

### Backend

- API REST feita com Express
- Separação entre rotas, controladores e serviços
- Validação de dados com biblioteca leve, como Zod ou express-validator
- Tratamento centralizado de erros
- Variáveis de ambiente via .env
- CORS habilitado para comunicação com o frontend

### Frontend

- Componentes reutilizáveis
- Layout organizado por páginas e módulos
- Chamadas à API isoladas em um módulo de serviços
- Context API para autenticação e dados globais
- Roteamento com React Router

## 4. Autenticação

- O sistema usará autenticação baseada em JWT.
- O professor e o estudante terão perfis distintos.
- A autenticação será responsável por identificar o usuário e autorizar acesso às rotas apropriadas.
- Permissões podem ser tratadas por perfil (ex.: professor vs estudante).

## 5. Banco de dados

- PostgreSQL será o banco principal.
- Prisma será usado para modelagem, migrações e acesso ao banco.
- A modelagem incluirá as entidades principais:
  - Professor
  - Estudante
  - Oportunidade
  - Inscricao
  - Recurso
  - HistoricoEscolar

## 6. Modelagem de domínio

### Professor
- nome
- email
- senha
- perfil
- oportunidades criadas

### Estudante
- nome
- matricula
- curso
- email
- senha
- historico escolar
- inscrições realizadas

### Oportunidade
- tipo
- descricao
- requisitos
- cursosPermitidos
- vagasSemBolsa
- vagasComBolsa
- dataCriacao
- dataInicioInscricao
- dataFimInscricao
- dataResultadoParcial
- dataInicioRecurso
- dataFimRecurso
- dataResultadoFinal
- professorResponsavel

### Inscricao
- estudante
- oportunidade
- historicoEscolar
- justificativaProfessor
- status
- dataInscricao
- recursoAssociado

### Recurso
- inscricao
- textoRecurso
- dataRecurso
- respostaProfessor
- status

## 7. Regras de negócio centrais

- A oportunidade pode ser de tipo: monitoria, pesquisa ou extensão.
- Pode aceitar estudantes de cursos específicos ou de todos os cursos.
- A oportunidade possui vagas sem bolsa e vagas com bolsa.
- O professor pode analisar alunos e indicar se estão aptos ou não.
- Quando não apto, a justificativa deve ser registrada.
- O estudante pode apresentar recurso em um período definido.
- O professor tem um ambiente separado para gestão e análise das inscrições.

## 8. Ambiente local

- Docker Compose será usado para subir PostgreSQL e a aplicação em ambiente local.
- Será configurado um arquivo .env para variáveis sensíveis.
- A aplicação local deve ter uma forma simples de executar:
  - backend
  - frontend
  - banco

## 9. Observações para didático

- O foco do projeto é a clareza do fluxo de negócio e da modelagem de dados.
- Não será priorizado um nível de sofisticação avançada de arquitetura.
- A implementação deve priorizar facilidade de leitura, manutenção e aprendizado.
- O projeto deve ser simples o suficiente para ser compreendido por estudantes em aulas ou exercícios acadêmicos.

## 10. Próximos passos sugeridos

1. Definir as entidades exatas no Prisma
2. Escrever os requisitos funcionais do sistema
3. Definir os casos de uso do professor e do estudante
4. Criar a estrutura inicial do backend e frontend
5. Implementar autenticação básica
6. Implementar o cadastro e listagem de oportunidades
7. Implementar inscrições e avaliação
8. Implementar recurso e resultados finais
