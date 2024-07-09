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
A API utiliza HATEOAS, incluindo links hipermídia nas respostas para permitir que os clientes naveguem dinamicamente pela API.
Este projeto atinge o Nível 3 do Modelo de Maturidade de Richardson, utilizando HATEOAS para fornecer links hipermídia nas respostas da API.

Modelo de Maturidade de Richardson
O Modelo de Maturidade de Richardson é uma forma de avaliar a conformidade de uma API com os princípios REST. Ele é composto por quatro níveis:

## Dependências do Maven

```xml
<dependencies>
    <dependency>
        <groupId>org.postgresql</groupId>
        <artifactId>postgresql</artifactId>
        <version>42.7.3</version>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-validation</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-hateoas</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>