# Projeto API RESTful com Spring Boot 3

Este projeto é uma API RESTful completa desenvolvida com Spring Boot 3, Spring Framework 6 e Java 17, seguindo o Modelo de Maturidade de Richardson. A API gerencia um catálogo de produtos com operações CRUD (Create, Read, Update, Delete).

## Estrutura do Projeto

<pre style="font-family: monospace;">
API [springboot]
├── .idea
├── .mvn
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com.example.springboot
│   │   │       ├── controllers
│   │   │       │   └── ProductController.java
│   │   │       ├── dtos
│   │   │       │   └── ProductRecordDto.java
│   │   │       ├── models
│   │   │       │   └── ProductModel.java
│   │   │       ├── repositories
│   │   │       │   └── ProductRepository.java
│   │   │       └── SpringbootApplication.java
│   ├── resources
│   │   └── application.properties
│   └── test
│       └── java
│           └── com.example.springboot
├── target
├── .gitignore
├── HELP.md
├── mvnw
├── mvnw.cmd
├── pom.xml
└── README.md
</pre>

## Configuração do Banco de Dados
Configure o banco de dados PostgreSQL no arquivo application.properties:

properties
Copiar código
spring.datasource.url=jdbc:postgresql://localhost:5432/springboot
spring.datasource.username=postgres
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.datasource.driver-class-name=org.postgresql.Driver
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect

## Endpoints da API
Nível 0: Serviços CRUD básicos
GET /products: Retorna a lista de produtos.
POST /products: Cria um novo produto.
GET /products/{id}: Retorna um produto específico.
PUT /products/{id}: Atualiza um produto específico.
DELETE /products/{id}: Remove um produto específico.
Nível 1: Recursos com URI's
O controlador de produtos (ProductController.java) gerencia os endpoints.

Nível 2: Métodos HTTP adequados
Os métodos HTTP GET, POST, PUT e DELETE são usados adequadamente para manipular os recursos.

Nível 3: HATEOAS
Os links HATEOAS são adicionados aos recursos retornados pela API.