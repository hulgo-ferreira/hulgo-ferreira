<img align="right" width="350" src="https://talkingabouttesting.files.wordpress.com/2015/01/tst-cloud.png"/>

# Olá! Sou Hulgo Rafael!👋
## 👩‍💻 QA Engineer | Test Automation | Quality Engineering

Profissional de Qualidade de Software com quase **6 anos de experiência** em testes manuais e automatizados, atuando em projetos de alta complexidade nos setores **financeiro, análises clínicas, gás** e em ambientes ágeis (Scrum).

Especialista em estratégias de testes, automação Front-end, validação de APIs e aplicação de Inteligência Artificial para otimização de processos de Quality Engineering.

🎓 **Pós-graduação em Engenharia de Qualidade e Testes de Software** — PUC Minas *(em andamento)*

[<img src="https://img.shields.io/badge/linkedin-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white" />](https://www.linkedin.com/in/hulgo-r-ferreira-806604a8/)[<img src="https://img.shields.io/badge/medium-%2312100E.svg?&style=for-the-badge&logo=medium&logoColor=white" />](https://medium.com/@hulgo.ferreira)

## 🛠️ Stack de Tecnologias

| Categoria | Ferramentas |
|-----------|------------|
| Automação | Selenium, Playwright, Cypress, Robot Framework |
| Linguagens | Python, JavaScript |
| CI/CD | Jenkins, Github Actions |
| Banco de Dados | MongoDB, SQL Server |
| Metodologias | Scrum, BDD |
| Especificação | Gherkin | 
| Gestão de Testes | Jira, Azure DevOps |
| Versionamento | GitLab, Github |

## 💻 Tecnologias

<p align="left"> <a href="https://robotframework.org/" target="_blank"> <img src="https://upload.wikimedia.org/wikipedia/commons/e/e4/Robot-framework-logo.png" alt="robot framework" width="40" height="40"/> </a> <a href="https://www.docker.com/" target="_blank"> <a href="https://www.python.org" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> <a href="https://www.ruby-lang.org/pt/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/ruby/ruby-original.svg" alt="ruby" width="40" height="40"/> </a> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="docker" width="40" height="40"/> </a> <a href="https://www.jenkins.io" target="_blank"> <img src="https://www.vectorlogo.zone/logos/jenkins/jenkins-icon.svg" alt="jenkins" width="40" height="40"/> </a> <a href="https://www.mongodb.com/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb" width="40" height="40"/> </a> <a href="https://www.microsoft.com/en-us/sql-server" target="_blank"> <img src="https://www.svgrepo.com/show/303229/microsoft-sql-server-logo.svg" alt="mssql" width="40" height="40"/> </a> <a href="https://www.oracle.com/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/oracle/oracle-original.svg" alt="oracle" width="40" height="40"/> </a> <a href="https://www.postgresql.org" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="40" height="40"/>

## ✅ Automação de Testes E2E do site [Swag Labs](https://www.saucedemo.com/) com Cypress - Funcionalidade Login

Este projeto demonstra a aplicação de boas práticas de Engenharia de Qualidade de Software (QA) na validação do fluxo de autenticação da plataforma Swag Labs. O objetivo principal é demonstrar maturidade no mapeamento de cenários de negócios, escrita de testes em formato BDD (Behavior-Driven Development) e automação robusta.

### ✅ Casos de Teste (BDD/Gherkin)

```gherkin
# language: pt
# cypress/features/login.feature

Funcionalidade: Realizar login com sucesso no Swag Labs
  Como um usuário do site Swag Labs
  Quero realizar o meu login
  Para acessar o catálogo de produtos

  CT01 - Login com credenciais válidas (positivo)
    Dado que estou na página de login do Swag Labs
    E possuo credenciais válidas cadastradas no sistema
    Quando preencho o campo "Username" com "standard_user"
    E preencho o campo "Password" com "secret_sauce"
    E clico no botão "Login"
    Então devo ser redirecionado para a página de produtos
    E o título "Products" deve ser exibido

  CT02: Login com credenciais inválidas (negativo)
    Dado que estou na página de login do Swag Labs
    Quando preencho o campo "Username" com "<usuario>"
    E preencho o campo "Password" com "<senha>"
    E clico no botão "Login"
    Então devo permanecer na página
    E a mensagem de erro "<mensagem>" deve ser exibida

    Exemplos:
    | usuario           | senha         | mensagem                                                                       |
    | usuario_invalido  | secret_sauce  | Epic sadface: Username and password do not match any user in this service      |
    | standard_user     | senha_errada  | Epic sadface: Username and password do not match any user in this service      |
    | usuario_invalido  | senha_errada  | Epic sadface: Username and password do not match any user in this service      |
    | (vazio)           | secret_sauce  | Epic sadface: Username is required                                             |
    | standard_user     | (vazio)       | Epic sadface: Username is required                                             |

```

## ✅ Estratégia de Testes

A cobertura do fluxo de login foi planejada com base em duas técnicas:

- **Partição de Equivalência** — agrupamento de inputs em classes válidas, inválidas e vazias, evitando testes redundantes
- **Análise de Valor Limite** — validação nas fronteiras de cada classe, onde bugs tendem a se concentrar

> 💡 Resultado: 4 cenários cobrem toda a superfície de risco do formulário, sem duplicação de esforço.

**Stack:** Cypress · JavaScript

<img width="1303" height="741" alt="image" src="https://github.com/user-attachments/assets/e97f54ae-638a-48e8-b25c-20b563c94401" />

## 🤖 Arquitetura da Automação (Cypress)

A arquitetura de automação implementada utiliza Custom Commands no Cypress para centralizar interações repetitivas, como logins, no arquivo **support/commands.js**, abstraindo ações para manter os testes limpos e reutilizáveis.

📎 [Ver Repositório](https://github.com/hulgo-ferreira/swaglabs-cypress-automation)

## ✅ Pipeline CI/CD — GitHub Actions

[![CI](https://github.com/hulgo-ferreira/swaglabs-cypress-automation/actions/workflows/ci.yml/badge.svg)](https://github.com/hulgo-ferreira/swaglabs-cypress-automation/actions)

A cada `push` ou `pull request`, a pipeline executa automaticamente:

1. 🔧 Instalação das dependências (`npm ci`)
2. 🧪 Execução dos testes E2E com Cypress (modo headless)
3. 📊 Geração automática do relatório Allure
4. 🚀 Publicação do relatório via GitHub Pages

> O relatório Allure pode ser acessado em: [https://hulgo-ferreira.github.io/swaglabs-cypress-automation/]

## 📊 Relatório de Execução (Allure) integrado ao Github

O relatório é gerado automaticamente após cada build e publicado via GitHub Pages.

📎 [Acessar último relatório →](https://hulgo-ferreira.github.io/swaglabs-cypress-automation/)

![Allure Report Preview](./docs/allure-preview.png) <!-- adicione um screenshot aqui -->

## 🏗️ Arquitetura do Projeto

<img width="323" height="576" alt="image" src="https://github.com/user-attachments/assets/6fed92cd-f614-4ef0-ab13-271c3593b119" />

## 📚 Publicações
- Artigo sobre "Testes Manuais e Automatizados": 
https://desenvolvimento.shift.com.br/testes-manuais-x-automatizados-um-substitui-o-outro-790a9e62e00
<!--
**hulgo-ferreira/hulgo-ferreira** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
