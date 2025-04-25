# Gerenciador de Tarefas - Spring Boot com MariaDB

Este é um projeto simples de gerenciamento de tarefas desenvolvido com Spring Boot, utilizando o banco de dados MariaDB para persistência. A aplicação permite realizar operações CRUD para usuários e suas respectivas tarefas.

## 📋 Pré-requisitos

Antes de executar o projeto, certifique-se de ter:

- Java JDK 11 ou superior
- XAMPP (com MariaDB)
- IDE como IntelliJ, Eclipse ou VS Code
- Postman (opcional, para testes)

## ⚙️ Configuração do Banco de Dados (MariaDB)

### 1. Instalar e iniciar o XAMPP

- Baixe o [XAMPP](https://www.apachefriends.org/index.html) e instale.
- Abra o painel de controle do XAMPP.
- Clique em "Start" no módulo **MariaDB**.

### 2. Criar o banco de dados `avaliacaonewton`

Acesse [http://localhost/phpmyadmin](http://localhost/phpmyadmin) e crie um novo banco chamado:

Ou execute no console SQL:

```sql
CREATE DATABASE avaliacaonewton;

### 3. Configurar application.properties

No arquivo src/main/resources/application.properties, configure as informações de acesso ao banco

### 🚀 Executando a Aplicação
1. Inicie o MariaDB pelo XAMPP
Verifique se o banco avaliacaonewton foi criado e está ativo.

2. Rode a aplicação no seu IDE
Execute a classe principal com a anotação @SpringBootApplication. Por padrão, a aplicação iniciará em:
http://localhost:8080

### 📮 Testando Endpoints 
Utilize o Postman ou outra ferramenta para testar os endpoints REST:

Endpoints de Usuário
POST /usuarios – Criar novo usuário

GET /usuarios – Listar usuários

PUT /usuarios/{id} – Atualizar usuário

DELETE /usuarios/{id} – Deletar usuário

Endpoints de Tarefa
POST /tarefas – Criar nova tarefa

GET /tarefas – Listar tarefas

PUT /tarefas/{id} – Atualizar tarefa

DELETE /tarefas/{id} – Deletar tarefa

-- Listar tabelas
SHOW TABLES;

-- Ver conteúdo da tabela de usuários
SELECT * FROM usuarios;

-- Ver conteúdo da tabela de tarefas
SELECT * FROM tarefas;

✅ Considerações Finais
Este projeto é uma base para aplicações com Spring Boot + MariaDB, usando arquitetura MVC. Pode ser facilmente expandido para incluir autenticação, relacionamentos mais complexos, e frontend.

