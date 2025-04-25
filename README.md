Gerenciador de Tarefas - Aplicação Spring Boot com MariaDB
Este projeto é um sistema de gerenciamento de tarefas desenvolvido em Spring Boot, com integração ao MariaDB para persistência de dados. O objetivo é permitir a criação, leitura, atualização e exclusão (CRUD) de usuários e tarefas.

Índice
Pré-requisitos

Configuração do Banco de Dados (MariaDB)

Instalação do XAMPP

Criação do Banco de Dados

Configuração do MariaDB

Configuração da Aplicação Spring Boot

Execução da Aplicação

Iniciar o MariaDB

Rodar o Projeto

Testes e Validação

Testando com Postman

Verificando no Banco de Dados

Considerações Finais

1. Pré-requisitos
Antes de iniciar a aplicação, verifique se as seguintes ferramentas estão instaladas no seu computador:

JDK 11+: Para compilar e executar a aplicação Java.

XAMPP: Para rodar o servidor de banco de dados MariaDB.

IDE de sua escolha: Pode ser IntelliJ IDEA, Eclipse, VSCode, etc.

Postman (opcional): Para testar os endpoints da API.

2. Configuração do Banco de Dados (MariaDB)
Instalação do XAMPP
Baixe e instale o XAMPP.

Abra o painel de controle do XAMPP e inicie o MariaDB clicando no botão "Start".

Criação do Banco de Dados
Acesse o phpMyAdmin através de http://localhost/phpmyadmin/.

Na aba "Databases", crie um banco de dados com o nome taskmanager.

Ou, se preferir, use o seguinte comando no MariaDB:

sql
Copiar
Editar
CREATE DATABASE taskmanager;
Configuração do MariaDB
Abra o arquivo src/main/resources/application.properties e ajuste a configuração de conexão com o banco de dados:

properties
Copiar
Editar
spring.application.name=gerenciador-de-tarefas
spring.datasource.url=jdbc:mariadb://localhost:3307/taskmanager
spring.datasource.username=root
spring.datasource.password=SUASENHA_AQUI (deixe vazio se não houver senha)
spring.datasource.driver-class-name=org.mariadb.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MariaDBDialect
Altere a porta e as credenciais conforme necessário.

3. Configuração da Aplicação Spring Boot
Abra seu projeto no IDE de sua escolha.

Certifique-se de que as dependências do Maven estejam configuradas corretamente no arquivo pom.xml para incluir o MariaDB e as outras bibliotecas necessárias para o Spring Boot.

4. Execução da Aplicação
Iniciar o MariaDB
Abra o XAMPP e clique em "Start" ao lado do MariaDB.

Verifique se o banco de dados taskmanager está disponível e ativo.

Rodar o Projeto
Abra o projeto no seu IDE.

Execute a aplicação Spring Boot (geralmente pela classe com a anotação @SpringBootApplication).

A aplicação será iniciada na porta 8080 (ou conforme configurado no application.properties).

5. Testes e Validação
Testando com Postman
Use o Postman para enviar requisições HTTP aos seguintes endpoints da API:

POST /usuarios: Criar um novo usuário.

GET /usuarios: Listar todos os usuários.

PUT /usuarios/{id}: Atualizar um usuário existente.

DELETE /usuarios/{id}: Excluir um usuário.

Faça as requisições e verifique se a resposta está correta.

Verificando no Banco de Dados
Após realizar as operações via API, você pode usar o phpMyAdmin ou comandos SQL no MariaDB para verificar se as alterações foram corretamente refletidas nas tabelas.

Exemplo de consulta SQL para listar os dados:

sql
Copiar
Editar
-- Verificar todas as tabelas
SHOW TABLES;

-- Verificar conteúdo da tabela de usuários
SELECT * FROM usuarios;

-- Verificar conteúdo da tabela de tarefas
SELECT * FROM tarefas;
6. Considerações Finais
Este projeto é uma implementação básica de um sistema de gerenciamento de tarefas, com foco em operações CRUD utilizando Spring Boot e MariaDB. Ele pode ser expandido para incluir funcionalidades adicionais como autenticação de usuários, mais detalhes nas tarefas, entre outros.

