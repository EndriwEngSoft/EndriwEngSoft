## Endriw Colvara Bento

Desenvolvedor backend Java em formação. Estudante de Engenharia de Software na Estácio, no 6º de 8 períodos. **Busco estágio ou vaga júnior em backend Java.**

Construo APIs REST com Java 21 e Spring Boot, com atenção a segurança, testes automatizados e deploy. Moro em Cerrito, RS (região de Pelotas).

---

### Projeto em destaque: LifeSync API

[![CI](https://github.com/EndriwEngSoft/lifesync-api/actions/workflows/ci.yml/badge.svg)](https://github.com/EndriwEngSoft/lifesync-api/actions/workflows/ci.yml)

API de produtividade pessoal com tarefas e subtarefas, hábitos com streak e histórico, e metas com progresso. Está em produção no Render, com banco PostgreSQL no Neon.

**[Repositório](https://github.com/EndriwEngSoft/lifesync-api)** · **[Testar no Swagger](https://lifesync-api-ezkx.onrender.com/swagger-ui/index.html)** (o primeiro acesso pode levar cerca de 1 minuto para acordar o servidor)

Decisões técnicas:

- **Proteção contra IDOR:** toda consulta é filtrada por `(id, userId)`. Recurso de outro usuário retorna `404`, não `403`, para não revelar que existe. Os IDs são UUID, não sequenciais.
- **JWT com access e refresh tipados:** um refresh token vazado não autentica rotas protegidas.
- **Check-in no fuso do usuário:** o "hoje" vem de um `Clock` injetado, não do fuso do servidor. Check-in duplicado é bloqueado no serviço e por uma constraint `UNIQUE` no banco, que cobre requisições simultâneas.
- **Schema versionado:** migrations com Flyway e `ddl-auto: validate`, conferidos por um teste de integração com Testcontainers contra PostgreSQL real.

Java 21 · Spring Boot 4.1 · Spring Security · JPA/Hibernate · PostgreSQL · Flyway · 65 testes (JUnit 5, Mockito, Testcontainers) · GitHub Actions · Docker

---

### Outros projetos

- **[FinanceSync API](https://github.com/EndriwEngSoft/financesync-api)**: API de finanças pessoais com conversão de moeda via API externa (Frankfurter). A cotação usada fica salva com a transação, e uma falha da API externa retorna `503`. Docker multi-stage, manifestos Kubernetes (Kustomize) e 102 testes.
- **[TaskFlow API](https://github.com/EndriwEngSoft/taskflow-api)**: API de tarefas com JWT stateless, isolamento por usuário, tratamento global de exceções e Swagger.
- **[Chess System](https://github.com/EndriwEngSoft/chess-system)**: xadrez no terminal em Java puro, com roque, en passant, promoção e xeque-mate. Projeto de estudo de orientação a objetos.

Estudos: [JPA/Hibernate](https://github.com/EndriwEngSoft/workshop-springboot4-jpa) · [MongoDB](https://github.com/EndriwEngSoft/workshop-springboot4-mongodb) · [JDBC e padrão DAO](https://github.com/EndriwEngSoft/demo-dao-jdbc)

---

### Stack

- **Backend:** Java 21, Spring Boot, Spring Security, JWT, JPA/Hibernate, Bean Validation
- **Bancos:** PostgreSQL, MongoDB, Flyway
- **Testes:** JUnit 5, Mockito, MockMvc, Testcontainers
- **Ferramentas:** Maven, Docker, GitHub Actions, Git, Swagger/OpenAPI

---

### Certificados

- [Formação Completa em Java: POO + Projetos](https://ude.my/UC-8553c0b3-a718-4212-b176-baf5ac058f09) (Udemy, fev/2026)
- [Testes com JUnit 5, Mockito e Spring Boot](https://www.udemy.com/certificate/UC-3b4fcf85-efef-44fe-bca5-daa8a0ee3885/) (Udemy, 2026)
- [Docker para Desenvolvedores](https://www.udemy.com/certificate/UC-e16c2fb7-9e22-40bb-8dde-3350ae539252/) (Udemy, Matheus Battisti, jun/2026)

---

### Contato

[LinkedIn](https://www.linkedin.com/in/endriw-bento/) · [endriwbento@gmail.com](mailto:endriwbento@gmail.com) · [Portfólio](https://endriwdev.vercel.app/)
