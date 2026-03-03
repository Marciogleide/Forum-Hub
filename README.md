🧠 ForumHub – API REST para Gerenciamento de Tópicos

API REST desenvolvida com Spring Boot para gerenciamento de tópicos de um fórum.
O projeto implementa operações completas de CRUD, validações de regras de negócio, persistência em banco relacional e autenticação com segurança baseada em tokens.

🚀 Objetivo do Projeto

Replicar o funcionamento do back-end de um fórum, permitindo:

Criar um novo tópico

Listar todos os tópicos

Visualizar um tópico específico

Atualizar um tópico

Excluir um tópico

A aplicação segue boas práticas do padrão REST e organização em camadas.

🛠 Tecnologias Utilizadas

Java 17

Spring Boot 3

Spring Web

Spring Data JPA

Spring Security

JWT (JSON Web Token)

PostgreSQL

Maven

🏗 Arquitetura

O projeto segue uma estrutura organizada por camadas:

forumhub/
│
├── controller/
├── domain/
│   ├── topic/
│   └── user/
├── security/
└── ForumhubApplication.java

Separação de responsabilidades:

Controller → Camada de entrada (HTTP)

Service → Regras de negócio

Repository → Persistência com JPA

Security → Autenticação e autorização

DTOs → Comunicação segura entre API e cliente

📌 Endpoints da API
🔐 Autenticação
Método	Rota	Descrição
POST	/login	Autenticação do usuário
📚 Tópicos
Método	Rota	Descrição
POST	/topics	Criar novo tópico
GET	/topics	Listar todos os tópicos
GET	/topics/{id}	Buscar tópico por ID
PUT	/topics/{id}	Atualizar tópico
DELETE	/topics/{id}	Remover tópico
🗄 Banco de Dados

Exemplo de estrutura básica:

CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    login VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL
);

CREATE TABLE topics (
    id SERIAL PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    message TEXT NOT NULL,
    created_at TIMESTAMP NOT NULL,
    active BOOLEAN DEFAULT TRUE
);
🔐 Segurança

A API utiliza:

Spring Security

Autenticação baseada em JWT

Proteção de rotas autenticadas

Senhas criptografadas

Fluxo:

Usuário faz login

API gera token JWT

Cliente envia token no header Authorization

API valida e libera acesso às rotas protegidas

▶️ Como Executar o Projeto
1️⃣ Clonar o repositório
git clone https://github.com/SEU_USUARIO/forumhub.git
2️⃣ Configurar banco de dados

Criar banco PostgreSQL chamado forumhub

Ajustar credenciais no application.properties

spring.datasource.url=jdbc:postgresql://localhost:5432/forumhub
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
3️⃣ Executar aplicação

Via Maven:

mvn clean install
mvn spring-boot:run

A API estará disponível em:

http://localhost:8080
🧪 Testes da API

Recomenda-se utilizar:

Postman

Insomnia

Exemplo de header para rotas protegidas:

Authorization: Bearer SEU_TOKEN_AQUI
📈 Evoluções Futuras

Paginação e ordenação

Tratamento global de exceções

Soft delete

Controle de perfis (ADMIN / USER)

Documentação com Swagger

Testes automatizados

Deploy em nuvem

🎯 Conceitos Aplicados

Arquitetura REST

Padrão MVC

DTO Pattern

Injeção de dependência

Validação com Bean Validation

Persistência com JPA

Autenticação stateless com JWT

👨‍💻 Autor

Marcio Gleide
Engenheiro de Computação# Forum-Hub
