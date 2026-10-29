# File Identifier

[English](README.md)

![File Identifier — identificação de tipo de ficheiro e língua do texto](assets/cover.svg)

O File Identifier é uma aplicação web em Java/Spring Boot que identifica o tipo MIME de um ficheiro e deteta a língua do seu texto. O utilizador envia um ficheiro ou indica um URL e recebe o nome, o tipo e a língua detetada.

Desenvolvido em equipa de dois estudantes para a cadeira de **Aplicações Distribuídas**.

## Análise de ficheiros

O Apache Tika identifica o tipo MIME a partir do conteúdo do ficheiro e extrai texto dos documentos. O Optimaize usa esse texto para estimar a língua. A deteção precisa de texto legível em quantidade suficiente; um ficheiro sem texto pode ter um tipo identificável, mas não um resultado de língua útil.

## Arquitetura

![Serviços e ligações HTTP do File Identifier](assets/architecture.svg)

O gateway encaminha os pedidos web para o frontend Thymeleaf. O frontend chama o serviço identificador através de OpenFeign e apresenta os resultados. O Eureka permite registar e localizar os serviços. O Docker Compose define os serviços e a rede que partilham.

O frontend guarda contas de utilizador e perfis numa base de dados H2 embebida, através de Spring Data JPA.

## Tecnologias

| Área | Tecnologias |
| --- | --- |
| Serviços | Java 19, Spring Boot 3, Spring Web |
| Encaminhamento e comunicação | Spring Cloud Gateway, Eureka, OpenFeign |
| Processamento de ficheiros | Apache Tika 2.6, Optimaize Language Detector |
| Interface web | Thymeleaf, HTML, CSS, JavaScript |
| Utilizadores e perfis | Spring Security, BCrypt, Spring Data JPA, H2 |
| Construção e contentores | Maven, Docker, Docker Compose |

## O meu contributo

Codesenvolvi a interface web, os endpoints de análise de ficheiros, a ligação entre serviços e a configuração Docker Compose.

O código-fonte é privado.
