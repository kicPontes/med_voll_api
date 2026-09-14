# 🏥 Med Voll API — Plataforma de Gerenciamento de Clínicas

![Java](https://img.shields.io/badge/Java-17-orange?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen?logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring%20Security-JWT-6DB33F?logo=springsecurity&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-Testcontainers-4479A1?logo=mysql&logoColor=white)
![Swagger](https://img.shields.io/badge/Docs-Swagger-85EA2D?logo=swagger&logoColor=black)
![JUnit](https://img.shields.io/badge/Tests-JUnit%205%20%7C%20Mockito-25A162?logo=junit5&logoColor=white)

API RESTful para o gerenciamento de uma clínica médica fictícia, com cadastro de médicos e pacientes e controle de agendamento de consultas. O desenvolvimento acompanhou a Formação Spring Boot da Alura (com Rodrigo Caneppele), com adaptações pessoais e testes adicionais.

## 📚 Conceitos Aplicados

✔ **Autenticação Stateless** — Login e proteção de rotas com Spring Security 6 + JWT, controlando acesso por perfil de usuário (roles)
✔ **Validação de Dados** — Bean Validation nos DTOs de entrada, barrando dados inconsistentes antes da camada de serviço
✔ **Testes de Integração Realistas** — Testcontainers sobe um banco MySQL real e descartável durante os testes, garantindo que o comportamento em teste seja o mesmo da produção
✔ **Documentação Viva da API** — Especificação OpenAPI/Swagger gerada a partir do código
✔ **Arquitetura em Camadas** — Separação clara entre `controller`, `service`, `domain` e `infra`

## ⚙️ Estrutura do Projeto

| Camada | Caminho | Responsabilidade |
|---|---|---|
| Controller | `/controller` | Expõe os endpoints REST |
| Domain | `/domain` | Entidades de domínio e repositórios (Médico, Paciente, Consulta, Endereço) |
| Service | `/service` | Regras de negócio da aplicação |
| Infra | `/infra` | Segurança, tratamento de exceções e configuração do Swagger |
| Tests | `/src/test` | Testes unitários e de integração |

## 🧩 Funcionalidades

- **Médicos** — cadastro, atualização, exclusão e listagem
- **Pacientes** — cadastro, atualização, exclusão e listagem
- **Consultas** — agendamento e gerenciamento de consultas médicas

## 🛠 Tecnologias Utilizadas

- **Backend:** Java 17, Spring Boot
- **Persistência:** Spring Data JPA · H2 (ambiente de desenvolvimento) · MySQL via Testcontainers (testes de integração)
- **Segurança:** Spring Security 6, JWT
- **Documentação:** Swagger / OpenAPI
- **Testes:** JUnit 5, Mockito, Testcontainers
- **Build:** Maven

## 🔍 O Que Aprendi (Key Takeaways)

- **Autenticação stateless:** como emitir e validar tokens JWT sem depender de sessão no servidor, e proteger rotas por perfil de usuário
- **Testes de integração confiáveis:** usar Testcontainers para validar a aplicação contra um banco real evita o clássico "funciona no H2, quebra em produção"
- **Validação em camadas:** Bean Validation como primeira linha de defesa da API contra dados malformados
- **Documentação como parte do desenvolvimento:** manter o Swagger atualizado como contrato vivo da API, facilitando o consumo por outros times

## ✅ Pré-requisitos

- Java 17
- Maven 3.8.1+

## 🚀 Como Executar

Clone o repositório:

```bash
git clone https://github.com/kicPontes/med_voll_api.git
cd med_voll_api
```

Compile o projeto e instale as dependências:

```bash
./mvnw clean install
```

Execute a aplicação:

```bash
./mvnw spring-boot:run
```

A aplicação estará disponível em `http://localhost:8080`.

## ⚙️ Configuração

O projeto usa **H2** em memória para o ambiente de desenvolvimento local — configuração em `src/main/resources/application.properties`. Nos testes de integração, o **Testcontainers** sobe automaticamente um container MySQL descartável, sem necessidade de configuração manual.

## 📄 Documentação da API

Disponível via Swagger em: `http://localhost:8080/swagger-ui.html`

## 🧪 Testes

```bash
./mvnw test
```

## 🙏 Agradecimentos

Projeto desenvolvido com apoio da Alura, na Formação Spring Boot com Rodrigo Caneppele.
