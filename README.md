[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/Du716tKn)

# Documentação Go com Zensical

## Sobre o Projeto

Este projeto foi desenvolvido para a disciplina de Collaboration Tools for Teams (CTT AP2), com o objetivo de criar um site de documentação da linguagem Go utilizando a ferramenta Zensical.

Além da produção da documentação técnica, o projeto teve como foco principal a aplicação de boas práticas de colaboração em equipe utilizando GitHub, Pull Requests, Code Review e automação de deploy com GitHub Actions.

---

# Tecnologias Utilizadas

* Go
* Markdown
* Zensical
* GitHub
* GitHub Actions
* Git
* Python

---

# Organização da Equipe

## 1. Especialista de Pipeline I (Triggers e Cache)

Luiz Henrique foi responsável pela configuração inicial do pipeline de automação.

### Atividades:

* Criação do workflow base do GitHub Actions
* Configuração dos gatilhos:

  * `pull_request`
  * `push`
  * `schedule`
* Implementação da estratégia de matriz (`strategy: matrix`)
* Configuração de cache com `actions/cache`
* Documentação:

  * Introdução e Instalação
  * Testes Automatizados em Go

---

## 2. Especialista de Pipeline II (Deploy e Segurança)

Diego Gonçalves foi responsável pela separação e segurança do pipeline de deploy contínuo.

### Atividades:

* Separação dos jobs:

  * `build_site`
  * `deploy_site`
* Uso da diretiva `needs`
* Upload e download de artefatos
* Implementação de condicionais (`if`)
* Bloqueio de deploy durante Pull Requests
* Documentação:

  * Sintaxe Básica e Variáveis
  * Gerenciamento de Pacotes (Go Modules)

---

## 3. Guardião do Repositório (Git Admin)

Gustavo silva foi responsável pelas regras de colaboração e proteção do repositório.

### Atividades:

* Inicialização do projeto Zensical
* Configuração de Branch Protection Rules
* Bloqueio de commits diretos na branch `main`
* Obrigatoriedade de Pull Requests
* Obrigatoriedade de Code Review
* Documentação:

  * Estruturas de Controle
  * Tratamento de Erros

---

## 4. Arquiteto de Informação (Zensical e UI)

Mellyssa Deborah foi responsável pela experiência visual da documentação.

### Atividades:

* Configuração do Syntax Highlighting para Go
* Organização da navegação lateral
* Padronização de tabelas
* Uso de Admonitions:

  * `warning`
  * `tip`
  * `note`
* Documentação:

  * Arrays, Slices e Maps
  * Structs e Métodos

---

## 5. Engenheiro de Concorrência e Qualidade

Pedro Henrique foi responsável pelos conteúdos avançados de Go e documentação final do projeto.

### Atividades:

* Criação do README.md
* Consolidação da arquitetura do workflow
* Organização final da documentação
* Registro dos integrantes do grupo
* Documentação:

  * Goroutines
  * Channels

---

# Fluxo de Trabalho da Equipe

O projeto seguiu um fluxo de trabalho colaborativo baseado em Feature Branches.

## Processo Utilizado

1. Cada integrante criou uma branch própria para desenvolver suas funcionalidades.
2. As alterações nunca foram realizadas diretamente na branch `main`.
3. Após finalizar a tarefa, o integrante abriu um Pull Request.
4. Outro membro da equipe realizou o Code Review.
5. Após aprovação, o Pull Request foi integrado à branch principal.

---

# Estrutura de Branches

## Exemplos:

```bash
feat/workflow-triggers
fix/deploy-pipeline
doc/go-deploy-security
```

---

# Proteção da Branch Main

Foram configuradas regras de proteção na branch `main` para garantir segurança e qualidade no desenvolvimento.

## Regras aplicadas:

* Bloqueio de push direto
* Obrigatoriedade de Pull Request
* Aprovação mínima de um integrante
* Revisão de código obrigatória

---

# Arquitetura do GitHub Actions

O pipeline foi dividido em dois jobs principais:

## 1. build_site

Responsável por:

* Instalar dependências
* Validar o projeto
* Gerar o site estático
* Salvar os artefatos HTML

---

## 2. deploy_site

Responsável por:

* Baixar os artefatos gerados
* Publicar o site no GitHub Pages

### Segurança:

O deploy nunca é executado durante Pull Requests.

---

# Estratégia de Matriz

Foi utilizada a diretiva:

```yaml
strategy:
  matrix:
    python-version: [3.10, 3.11]
```

Essa estratégia garante que o projeto funcione corretamente em diferentes versões do Python.

---

# Cache de Dependências

Foi utilizada a action:

```yaml
actions/cache
```

Objetivo:

* Melhorar a performance do pipeline
* Evitar reinstalações desnecessárias de dependências

---

# Estrutura do Projeto

```text
docs/
├── arrays-slices-maps.md
├── channels.md
├── go-modules.md
├── goroutines.md
├── index.md
├── instalacao.md
├── introducao.md
├── markdown.md
├── sintaxe-basica.md
├── structs-metodos.md
├── testes-automatizados.md

.github/
└── workflows/
    └──deploy.yml

.gitignore
README.md
zensical.toml


---

# Recursos Visuais da Documentação

O projeto utilizou recursos do Zensical para melhorar a experiência de leitura:

* Syntax Highlighting para Go
* Alertas e avisos (Admonitions)
* Navegação lateral organizada
* Tabelas estruturadas
* Blocos de código formatados

---

# Publicação

O site foi publicado utilizando GitHub Pages através de deploy automatizado com GitHub Actions.

---

# Consolidação Final do Projeto

A arquitetura final do workflow do GitHub Actions foi construída de forma colaborativa pelos membros responsáveis pelos pipelines CI/CD do projeto.

O processo de automação foi dividido em dois jobs principais:

| Job           | Responsabilidade                                |
| ------------- | ----------------------------------------------- |
| `build_site`  | Validação do projeto e geração do site estático |
| `deploy_site` | Publicação automática no GitHub Pages           |

O job `build_site` ficou responsável pela instalação das dependências, validação do projeto e geração dos arquivos HTML da documentação. Além disso, foi utilizada uma estratégia de matriz (`strategy: matrix`) para validar o funcionamento do projeto em diferentes versões do Python.

Também foi implementado cache de dependências utilizando `actions/cache`, reduzindo o tempo de execução do pipeline e evitando reinstalações desnecessárias.

O job `deploy_site` foi configurado para aguardar a conclusão do `build_site` utilizando a diretiva `needs:`. Após isso, o workflow realiza o download dos artefatos gerados e publica automaticamente o site no GitHub Pages.

Para garantir maior segurança no fluxo CI/CD, foi aplicada uma condicional (`if`) impedindo que o deploy seja executado durante Pull Requests, permitindo publicação apenas em eventos de `push` na branch `main` e execuções agendadas (`schedule`).

O fluxo completo do pipeline ficou organizado da seguinte forma:

```text
Pull Request / Push / Schedule
            ↓
       build_site
            ↓
      upload-artifact
            ↓
       deploy_site
            ↓
      GitHub Pages
```

Essa arquitetura permitiu maior organização, automação, segurança e separação de responsabilidades no desenvolvimento colaborativo do projeto.

---

# Integrantes do Grupo

| Integrante              | RA      | Responsabilidade                       |
| ----------------------- | ------- | -------------------------------------- |
| Luiz Henrique           | 2501545 | Pipeline I (Triggers e Cache)          |
| Diego Gonçalves         | 2501113 | Pipeline II (Deploy e Segurança)       |
| Mellyssa Deborah        | 2403866 | Arquiteto de Informação                |
| Gustavo Silva           | 2403815 | Guardião do Repositório                |
| Pedro Henrique Cespedes | 2500860 | Engenheiro de Concorrência e Qualidade |
